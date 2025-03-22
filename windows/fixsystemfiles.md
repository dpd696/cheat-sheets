# Fix Corrupt System Files with SFC & DISM
If your Windows system is acting up, these built-in tools can scan and repair corrupted system files automatically!

## Command Prompt (Administrator)
Open Command Prompt (Admin)

### Execute Command for SFC
```cmd
SFC /scannow
```

### Execute Command for DISM
```cmd
DISM /Online /Cleanup-Image /Restorehealth
```
