# Portfolio workspace backup — 21 October 2026

This branch preserves the workspace files, including ignored personal projects and local modifications. Website files are also saved on main.

Download or clone this branch, then run the following PowerShell commands from its folder to restore:

```powershell
$archive = [IO.File]::Create((Join-Path (Get-Location) 'portfolio-backup.tar.gz'))
Get-ChildItem 'portfolio-backup.part-*' | Sort-Object Name | ForEach-Object {
    $part = [IO.File]::OpenRead($_.FullName)
    $part.CopyTo($archive)
    $part.Dispose()
}
$archive.Dispose()
Get-FileHash portfolio-backup.tar.gz -Algorithm SHA256
# Compare the result with archive-sha256.txt before extracting.
New-Item -ItemType Directory restored -Force
 tar -xzf portfolio-backup.tar.gz -C restored
```

See files.txt for included paths and backup-details.json for exclusions. Reinstall Python environments and other dependencies. Git internals and local service settings are excluded; clone original repositories separately if their history is needed. Credentials are excluded. Keep all archive parts together.

Archive verification: all 5,425 readable selected files are present. One Windows reserved-name entry, RESUME_ABHISHEK/ETC/ETC_QL_RW/nul, could not be archived.
