# Product Software Artifacts

Private archive of the supplied Debate Table, Sovereign Enterprise, and SOW production packages, reports, raw-source exports, and independent-review record.

## Integrity

`SHA256SUMS.txt` records a SHA-256 digest for every supplied artifact. Verify from PowerShell with:

```powershell
Get-Content .\SHA256SUMS.txt | ForEach-Object {
    $hash, $name = $_ -split '  ', 2
    [pscustomobject]@{
        File = $name
        Valid = (Get-FileHash -LiteralPath $name -Algorithm SHA256).Hash -eq $hash
    }
}
```

The source files in `D:\Product Software` were copied without modification.
