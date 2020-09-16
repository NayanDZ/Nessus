# Nessus


## Pre-Requisite for OS VA Scan     

Please make sure following points should be configured for server scanning:

1. The Windows Management Instrumentation (WMI) service must be enabled on the target. (https://technet.microsoft.com/en-us/library/cc180684.aspx)
2. The Remote Registry service must be enabled on the target.
3. Firewall should be disable on target server(Disable Server level Firewall).
4. File & Printer Sharing must be enabled in the target's network configuration.
5. An SMB account must be used that has local administrator rights on the target. (You can use a domain account, but that account must be a local administrator on the devices being scanned.)
6. All ports must be open between the Nessus scanner and the target (ANY to ANY).
7. Enable Service.msc (Workstation/Server)
8. Ensure that no Windows security policies are in place that block access to these services.
9. The default administrative shares (i.e. IPC$, ADMIN$, C$) must be enabled (AutoShareServer = 1). Windows 10 has the ADMIN$ disabled by default. For all other OS's, these shares are enabled by default and can cause other issues if disabled (http://support.microsoft.com/kb/842715/en-us).

**Note:-** The above mentioned pre-requisite and configuration points are required and necessary to have the scan completed successfully without any errors and false positive findings.


## Troubleshooting 
1. Ping IP from Nessus server
```javascript
ping (IP Address) 
```

2. Telnet from Nessus server
```javascript
telnet (IP Address) 22

AND

telnet (IP Address) 139

OR

telnet (IP Address) 445
```

3. Traceroute  
```javascript
tracert (IP Address)
```

4. Map Network Drive
```javascript
\\IP\admin$   [- Win32 access]

AND

\\IP\IPC$     [- C drive access]
```







