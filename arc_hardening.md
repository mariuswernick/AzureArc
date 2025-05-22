# Azure Arc-Enabled Server Hardening

This document provides PowerShell commands to harden your Azure Arc-enabled servers. These steps help reduce the attack surface and improve security.

## 1. Allow Only Approved Extensions
```powershell
azcmagent config set extensions.allowlist "Microsoft.SoftwareUpdateManagement/WindowsOsUpdateExtension"
```

## 2. Disable Guest Configuration
```powershell
azcmagent config set guestconfiguration.enabled false
```

## 3. Disable Incoming Connections
```powershell
azcmagent config set incomingconnections.enabled false
```

## 4. Disable Local User Creation via Arc
```powershell
azcmagent config set localuser.enabled false
```

## 5. Enforce Secure Communication (HTTPS Only)
```powershell
azcmagent config set httpsonly.enabled true
```

## 6. Enable Logging for Arc Agent Actions
```powershell
azcmagent config set logging.enabled true
```

## 7. Restrict Extension Auto-Upgrade (Optional)
```powershell
azcmagent config set extensions.autoupgrade.enabled false
```

## 8. Regularly Update the Arc Agent
```powershell
azcmagent upgrade
```

> **Note:**
> - Adjust the allowlist as needed for your environment.
> - Some settings may require the latest version of the Azure Connected Machine Agent.
> - Test these settings in a non-production environment before wide deployment.
