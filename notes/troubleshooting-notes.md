# Troubleshooting Notes

## Issue 1

Unable to create SMB share.

### Cause

PowerShell was not running as Administrator.

### Resolution

Open PowerShell using **Run as Administrator** before executing:

```powershell
New-SmbShare
```

---

## Issue 2

DFIRShare not listed.

### Cause

Share creation failed.

### Resolution

Verify using:

```powershell
Get-SmbShare
```

---

## Issue 3

Unable to access:

```
\\localhost\DFIRShare
```

### Cause

Incorrect share name or share creation failure.

### Resolution

Verify the share exists before attempting access.

---

## Issue 4

Get-SmbSession returned no results.

### Cause

Localhost access does not always generate an SMB session.

### Resolution

Expected behavior. Remote client connections will normally produce active session records.

---

## Issue 5

Get-SmbOpenFile returned no results.

### Cause

No active remote SMB file handles.

### Resolution

Keep the shared folder open or connect from another Windows computer for more realistic results.

---

## Issue 6

Unable to remove SMB share.

### Cause

The share was still being accessed.

### Resolution

Close File Explorer and run:

```powershell
Remove-SmbShare -Name DFIRShare -Force
```
