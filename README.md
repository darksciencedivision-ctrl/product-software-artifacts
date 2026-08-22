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

## Superseded (2026-08-22)

This flat archive is kept as-is for history. The same material — plus the Sovereign Distillery bundles, the
SOW round-2 raw reports and the SWS-UI-001 workspace itself — is now organized, one private repository per
project, with the workspace repository vendoring all of them:

- [`sovereign-production-workspace`](https://github.com/darksciencedivision-ctrl/sovereign-production-workspace) — SWS-UI-001 Sovereign Workspace Shell v1.2 + all four deliverable sets (the one project that completes the four)
- [`sovereign-enterprise-production`](https://github.com/darksciencedivision-ctrl/sovereign-enterprise-production) — SOVEREIGN 3.1.2
- [`debate-table-production`](https://github.com/darksciencedivision-ctrl/debate-table-production) — Debate Table v1.2 Phase 1
- [`sow-multi-model-terminal`](https://github.com/darksciencedivision-ctrl/sow-multi-model-terminal) — SOW baseline + independent review
- [`sovereign-distillery-enterprise`](https://github.com/darksciencedivision-ctrl/sovereign-distillery-enterprise) — Distillery enterprise snapshot `5ff6f56e`

Note: `Debate_Table_v1.2_Phase1_Production_20260811_201116 - Copy.zip` here hashes `29b364b0…`, not the `be6cfe8c…`
its adjacent `.sha256` records — the copy carries an appended `SOW_REVIEW_ROUND2_RAW/` folder; see the
`debate-table-production` README.
