# Troubleshooting Notes

## Issue 1

We are unable to create SMB share

### Cause

PowerShell was not running as Administrator.

### Resolution

Open PowerShell using **Run as Administrator** before executing:

```powershell
New-SmbShare
```

---

## Issue 2

DFIRShare not there.

### Cause

Not able to create share.

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

Incorrect share name or share creation failed.

### Resolution

Verify whether the share exists or not.

---

## Issue 4

Get-SmbSession gives me no results.

### Cause

Localhost access does not always generate an SMB session.

### Resolution

Expected behavior. 

---

## Issue 5

Get-SmbOpenFile returned no results.

### Cause

No active remote SMB file handles.

### Resolution

Keep the shared folder open or connect from another Windows computer for more realistic results.

---

