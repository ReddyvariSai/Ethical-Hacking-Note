TCP communication flags are control bits within the TCP header used to manage the state of a connection. They tell the receiving device how to interpret the packet and what action to take. In the context of network scanning, understanding these flags is essential because different scan types (SYN scan, FIN scan, NULL scan) rely on manipulating these flags to evade detection or bypass firewalls.

Here is a detailed breakdown of the eight TCP control flags (the "flag octet") as they function today.

### 📡 The 8 TCP Flags (Control Bits)
The flags field is 8 bits long. The original specification (RFC 793) defined six flags. Three additional flags have been added over time (NS, CWR, ECE) for congestion control, though CWR and ECE are often grouped as "ECN" flags.

| **Flag** | **Bit Position** | **Name** | **Function** |
|:---|:---:|:---|:---|
| **NS** | 0 | **Nonce Sum** | Used for ECN (Explicit Congestion Notification) protection against accidental or malicious concealment of marked packets. |
| **CWR** | 1 | **Congestion Window Reduced** | Sent by the sender to indicate it received a packet with the ECE flag and has reduced its transmission rate. |
| **ECE** | 2 | **ECN-Echo** | Indicates the sender is ECN-capable. If set during the handshake, the device supports ECN. If set during data transfer, it signals congestion. |
| **URG** | 3 | **Urgent** | Marks the packet as high priority. Indicates that the **Urgent Pointer** field is significant and contains out-of-band data. (Rarely used in modern networks). |
| **ACK** | 4 | **Acknowledgment** | Confirms receipt of data. Indicates that the **Acknowledgment Number** field is valid. **Always set** after the initial SYN packet in a connection. |
| **PSH** | 5 | **Push** | Instructs the receiving system to send the buffered data directly to the application **immediately**, bypassing buffers. (e.g., in an interactive SSH session). |
| **RST** | 6 | **Reset** | Abruptly tears down the connection. Sent when a packet arrives for a non-existent socket or when a host wants to reject a connection. |
| **SYN** | 7 | **Synchronize** | Initiates a connection. Used in the first step of the three-way handshake to synchronize sequence numbers. |
| **FIN** | 8 | **Finish** | Gracefully terminates a connection. Indicates the sender has no more data to send. |

> **Note**: The ordering of bits can vary depending on whether the header is being read in network byte order or being visualized. The list above represents the bit order transmitted over the wire (most significant to least significant).

---

### 🔁 The Three-Way Handshake (SYN, SYN-ACK, ACK)
This is the most common interaction of TCP flags. It establishes a reliable connection.

1.  **SYN**: Client sends a packet with the **SYN** flag set. (Seq=X)
2.  **SYN-ACK**: Server responds with **SYN** and **ACK** flags set. (Seq=Y, Ack=X+1)
3.  **ACK**: Client sends a packet with the **ACK** flag set. (Seq=X+1, Ack=Y+1)

Once this exchange is complete, data transfer begins, typically using the **PSH** and **ACK** flags.

---

### 🛡️ How Flags Are Used in Network Scanning
Security professionals (and attackers) manipulate TCP flags to map networks and evade detection.

**1. SYN Scan (Stealth / Half-Open Scan)**
- **Flags Sent**: `SYN`
- **Response Analysis**:
    - `SYN-ACK` = Port is **Open**.
    - `RST` = Port is **Closed**.
    - No Response / ICMP Unreachable = Port is **Filtered** (blocked by firewall).
- **Why "Stealth"?** The scanner never completes the three-way handshake; it sends a `RST` after receiving the `SYN-ACK` to reset the connection. This avoids logging on older systems (though modern IDS/IPS detect it easily).

**2. FIN Scan**
- **Flags Sent**: `FIN`
- **Response Analysis**:
    - `RST` = Port is **Closed** (RFC compliant).
    - No Response = Port is **Open|Filtered**.
- **Use Case**: Bypasses stateless firewalls and some non-RFC compliant filters that block SYN packets but allow FIN packets.

**3. NULL Scan**
- **Flags Sent**: **None** (Flags field set to 0).
- **Response Analysis**: Same as FIN scan.
- **Use Case**: Attempts to evade filters by looking like random garbage traffic.

**4. XMAS Scan**
- **Flags Sent**: `FIN` + `PSH` + `URG` (Packet is "lit up" like a Christmas tree).
- **Response Analysis**: Same as FIN/NULL scans.
- **Use Case**: Evasion based on packet anomaly.

**5. ACK Scan**
- **Flags Sent**: `ACK`
- **Response Analysis**: Does *not* determine open/closed. Used to **map firewall rules**.
    - `RST` = Port is **Unfiltered** (accessible).
    - No Response / ICMP Error = Port is **Filtered** (stateful firewall is dropping the packet).

**6. RST Scan**
- **Flags Sent**: `RST`
- **Response**: Generally ignored or kills an existing connection. Not typically used for discovery, but for disruption.

---

### ⚠️ Important Context for 2025
While the flags themselves have not changed since the addition of ECN flags, **their effectiveness in scanning has diminished**:

1.  **Stateful Inspection**: Modern firewalls and cloud security groups (AWS Security Groups, Azure NSGs) do not care about the flag combination. If a packet is unsolicited and not part of an existing connection, it is often simply dropped, returning a "Filtered" result regardless of whether the port is actually open .
2.  **Rate Limiting**: Aggressive flag manipulation triggers rate-limiting and automatic IP blacklisting (fail2ban, CrowdSec, cloud WAFs).
3.  **Evasion is Hard**: Techniques like FIN, NULL, and XMAS scans are largely obsolete against modern infrastructure unless specifically targeting legacy embedded systems or poorly configured BSD-based firewalls.

**Practical Takeaway**: The **SYN scan** remains the gold standard for speed and reliability. The exotic flag scans (FIN, XMAS) are now primarily used for academic learning or targeting specific deprecated environments rather than general reconnaissance.
