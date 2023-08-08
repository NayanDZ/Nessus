# Nessus

## Download & Activate Nessus

1. Download Tenable Nessus: https://www.tenable.com/downloads/nessus?loginAttempted=true

2. Install Tenable Nessus Offline: https://docs.tenable.com/nessus/Content/InstallNessusOffline.htm#Generate-the-License

3. Generate the License: https://plugins.nessus.org/v2/offline.php

4. Click the Submit button. The Offline Update Page Details appears and shows the following details:

  **Custom URL:** The custom URL displayed downloads a compressed plugins file. This file is used by Nessus to obtain plugin information. This URL is specific to your Nessus license and must be saved and used each time plugins need to be updated.

5. Download and Copy Latest Plugins compressed TAR file to the Nessus system

```
Use the directory specific to your operating system:

Linux
# /opt/nessus/sbin/

Windows
C:\Program Files\Tenable\Nessus

macOS
# /Library/Nessus/run/sbin/
```
6. Install Plugins Manually
```
Install plugins manually using the command-line interface

Linux
# /opt/nessus/sbin/nessuscli update <tar.gz filename>

Windows
C:\Program Files\Tenable\Nessus>nessuscli.exe update <tar.gz filename>

macOS
# /Library/Nessus/run/sbin/nessuscli update <tar.gz filename>
```


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







