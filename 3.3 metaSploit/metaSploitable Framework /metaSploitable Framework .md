The **Metasploitable Framework** isn't a single, official tool, but the term is often used to refer to intentionally **vulnerable systems and environments** designed for learning penetration testing and security research. The most famous examples are:

## 1. **Metasploitable 2**
The classic vulnerable VM created by Rapid7 (Metasploit's developer).

**Purpose:** A deliberately insecure Ubuntu Linux VM for practicing penetration testing.

**Vulnerabilities included:**
- Backdoored services (vsftpd, UnrealIRCd)
- Weak credentials
- Web vulnerabilities (DVWA, Mutillidae)
- Misconfigured services
- Outdated software (Samba, Apache, PHP)
- SQL injection opportunities

**Download:** Available from SourceForge or Rapid7's site

## 2. **Metasploitable 3**
The newer, more advanced version (Windows-based build system).

**Features:**
- Builds fresh VMs from scratch using Packer and Vagrant
- Two versions: Ubuntu and Windows Server 2008
- More realistic enterprise environment
- Modern vulnerabilities

## 3. **Metasploit Framework Itself**
The actual penetration testing platform:
- **msfconsole**: Main interface
- **Auxiliary modules**: Scanning, fuzzing, reconnaissance
- **Exploit modules**: Actual vulnerability exploitation
- **Payloads**: Shells, Meterpreter
- **Post-exploitation modules**

## **Legal & Ethical Use**
⚠️ **CRITICAL WARNING:**
- **Only use on your own isolated lab**
- Never scan/attack systems you don't own
- These VMs are intentionally vulnerable - keep offline
- Use with virtual networks (NAT/host-only)

## **Learning Path**
1. **Start with Metasploitable 2** - simpler, well-documented
2. **Practice with Metasploit Framework** against it
3. **Move to Metasploitable 3** for more challenges
4. **Explore web apps** (DVWA, WebGoat) within them

## **Common Practice Scenarios**
- Service enumeration and scanning
- Exploit development practice
- Privilege escalation exercises
- Post-exploitation practice
- Web application security testing

## **Alternatives**
If you're looking for similar learning environments:
- **DVWA** (Damn Vulnerable Web App)
- **OWASP WebGoat/Juice Shop**
- **VulnHub** (many vulnerable VMs)
- **HackTheBox** (more controlled)

**Remember:** These are training tools, not real hacking tools for unauthorized use. They exist to help security professionals learn defense through understanding offense.

Would you like guidance on setting up a safe lab environment or specific exercises to try with Metasploitable?
