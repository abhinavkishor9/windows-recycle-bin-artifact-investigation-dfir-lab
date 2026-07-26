# Troubleshooting Notes

## Issue 1

Unable to access Recycle Bin.

### Cause

Hidden system files were not visible.

### Resolution

Enabled:

- Show hidden files
- Unchecked "Hide protected operating system files"

---

## Issue 2

SID folder not visible.

### Cause

Recycle Bin had no deleted files.

### Resolution

Delete sample files first.

---

## Issue 3

PowerShell returned no files.

### Cause

Incorrect SID path.

### Resolution

List SID folders first:

```powershell
Get-ChildItem 'C:\$Recycle.Bin' -Force
```

---

## Issue 4

Unable to open $I file.

### Cause

Attempted to use Get-Content.

### Resolution

Use:

```powershell
Start-Process "<I File>"
```

---

## Issue 5

Unable to read recovered contents.

### Cause

Using Get-Content on Office documents.

### Resolution

Open using:

```powershell
Start-Process "<R File>"
```

---

## Issue 6

Recycle Bin empty.

### Cause

Files permanently deleted.

### Resolution

Repeat the lab by deleting fresh sample files.
