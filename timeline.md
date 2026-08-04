# Investigation Timeline

| Time | Activity | Evidence |
|------|----------|----------|
| 09:00 | Created investigation workspace | SMBLab |
| 09:05 | Created sample investigation files | Payroll.txt, Finance.txt |
| 09:10 | Created SMB share | New-SmbShare |
| 09:15 | Verified shared folder | Get-SmbShare |
| 09:20 | Accessed shared folder | File Explorer |
| 09:25 | Reviewed SMB sessions | Get-SmbSession |
| 09:30 | Reviewed open SMB files | Get-SmbOpenFile |
| 09:35 | Examined SMB server configuration | Get-SmbServerConfiguration |
| 09:40 | Correlated investigation findings | Documentation |
| 09:45 | Removed lab artifacts | Remove-SmbShare |

---

# Investigation Flow

Investigation Started

↓

Created Investigation Workspace

↓

Created Sample Files

↓

Created SMB Share

↓

Verified SMB Share

↓

Accessed Shared Folder

↓

Reviewed SMB Sessions

↓

Reviewed Open Files

↓

Examined SMB Server Configuration

↓

Correlated Findings

↓

Removed Lab Artifacts

↓

Investigation Completed

---

# Summary

The investigation demonstrated how Windows SMB shares can be created, enumerated, and analyzed using native PowerShell. The lab introduced the commands used to investigate SMB sessions, shared resources, and server configuration while emphasizing that localhost testing may not always produce active SMB session artifacts. The workflow reflects the same methodology used during enterprise DFIR investigations involving Windows file-sharing activity.
