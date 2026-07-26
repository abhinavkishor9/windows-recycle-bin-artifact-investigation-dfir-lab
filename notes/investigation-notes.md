# Investigation Notes

## Lab Summary

Objective:

Investigate Windows Recycle Bin forensic artifacts by examining the relationship between $I metadata files and $R recovered file contents.

---

## Analyst Methodology

The investigation followed a standard host-based DFIR methodology:

1. Prepare controlled evidence.
2. Generate deletion activity.
3. Preserve artifacts.
4. Locate forensic evidence.
5. Examine metadata.
6. Recover deleted content.
7. Correlate findings.
8. Document evidence.
9. Produce investigation timeline.

---

## Investigation Steps

### Step 1

Created investigation folders.

Evidence:
- Finance
- HR
- IT
- Reports

---

### Step 2

Created sample files.

Evidence:
- Payroll.xlsx
- Employees.txt
- Passwords.txt
- IncidentReport.docx

---

### Step 3

Deleted selected files.

Observation:

Deleted files appeared inside the Windows Recycle Bin.

---

### Step 4

Located:

```
C:\$Recycle.Bin
```

Observed the user SID folder.

---

### Step 5

Entered the SID folder.

Observed:

- $I files
- $R files

---

### Step 6

Opened the $I file.

Observation:

Recovered metadata showing:

- Original filename
- Original path

---

### Step 7

Opened the corresponding $R file.

Observation:

Recovered deleted file contents successfully.

---

### Step 8

Correlated:

| Metadata | Recovered Content |
|-----------|------------------|
| $I | $R |

Confirmed matching deleted file.

---

## Evidence Summary

Collected:

- PowerShell outputs
- Recycle Bin screenshots
- SID folder
- $I artifacts
- $R artifacts

---

## Analyst Observations

The investigation demonstrated that:

- Windows stores deleted file metadata separately from file content.
- $I files contain forensic metadata used to identify deleted items.
- $R files preserve the recoverable contents of deleted files until the Recycle Bin is emptied.
- Correlating both artifacts enables investigators to reconstruct deletion events accurately.

---

## Conclusion

The investigation successfully demonstrated Windows Recycle Bin forensic analysis by identifying deleted files, recovering file contents, and correlating metadata with recovered evidence using native Windows tools.
