**NetBIOS** (Network Basic Input/Output System) is a service that allows applications on different computers to communicate with each other over a local area network (LAN).

Developed in the 1980s, it was the primary method for file and printer sharing in early Windows networks (Windows 95, 98, NT, and 2000).

### Key Characteristics

- **Not a Protocol, but an API:** NetBIOS provides a set of commands (an Application Programming Interface) for naming, session management, and datagram services. It relies on transport protocols like NetBEUI, IPX/SPX, or TCP/IP to actually move the data.
- **NetBIOS over TCP/IP (NBT):** This is the most common modern implementation. It allows NetBIOS to run over the TCP/IP protocol. It uses three specific ports:
    - **UDP 137:** Name services (registering and finding computer names).
    - **UDP 138:** Datagram services (connectionless communication).
    - **TCP 139:** Session services (connection-oriented communication for file and printer sharing).

### How It Works (Naming)

NetBIOS identifies computers by a unique 15-character **NetBIOS name** (often the computer's name). When a computer joins the network, it broadcasts its name to ensure it is unique. To find a resource (like a shared folder named `\\SERVER\Public`), a computer broadcasts a request asking, "Who has the name SERVER?"

### Why It Is Obsolete

NetBIOS is considered a legacy protocol and is largely deprecated in modern Windows environments (Windows Vista, 7, 8, 10, 11, and Server editions) for the following reasons:

1.  **Security:** It is highly vulnerable to attacks.
    - **Man-in-the-Middle:** Attackers can listen to name resolution requests and respond, redirecting traffic to malicious servers.
    - **Information Disclosure:** It can leak internal network names and structures.
2.  **Inefficiency:** It relies heavily on broadcasts. A machine requesting a name lookup sends a message to *every* machine on the network segment, increasing unnecessary traffic. This does not scale well on large networks.
3.  **Lack of Internet Support:** It is non-routable by design in its native form (NetBEUI). While NBT allows it to traverse routers, it is not designed for the security and complexity of the internet.
4.  **Modern Alternatives:** Modern networks use **DNS (Domain Name System)** for name resolution and direct **SMB (Server Message Block)** connections over port 445, which are more secure, efficient, and routable.

### NetBIOS Today

- **Default Status:** In modern Windows, NetBIOS over TCP/IP is often **enabled by default** for backward compatibility with older devices (like legacy printers or industrial machines).
- **Disabling:** For security hardening, system administrators often disable NetBIOS over TCP/IP on network adapters, especially for computers directly exposed to the internet or in well-controlled domains where DNS is fully functional.
- **SMB Conflict:** You will often hear about NetBIOS when troubleshooting SMB (Samba/Windows file sharing) issues, specifically whether to use port 139 (NetBIOS session) or port 445 (direct SMB).
