## WinGet manifest creation and validation

[Windows Package Manager Manifest Creator](https://github.com/microsoft/winget-create)

### Update existing package
```powershell
# PackageId such as BryanCandi.BandwidthCalculator
wingetcreate update <PackageId> --interactive
```

### Testing and Validation
- Testing with Windows 11 Sandbox:
```powershell
C:\PATH_TO_REPO\winget-pkgs\Tools\SandboxTest.ps1 C:\Users\user\manifests\p\Publisher\App\1.2.3
```

- Manual validation and installation:
```powershell
# Validate local manifest before submission
winget validate --manifest C:\Users\user\manifests\p\Publisher\App\1.2.3
```
```powershell
# Installs directly from local manifest (not from winget repo)
winget install --manifest C:\Users\user\manifests\p\Publisher\App\1.2.3
```

### Submit manifest after updating or editing
```powershell
wingetcreate.exe submit C:\Users\user\manifests\p\Publisher\App\1.2.3
```

### New package
```powershell
wingetcreate new --interactive
```
