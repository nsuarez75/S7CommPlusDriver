# PLC-Monitor fork — modification notice

Fork of [dotnetprojects/S7CommPlusDriver](https://github.com/dotnetprojects/S7CommPlusDriver)
(itself derived from [thomas-v2/S7CommPlusDriver](https://github.com/thomas-v2/S7CommPlusDriver)),
licensed under the GNU LGPL v3 or later (see `LICENSE`). Base commit: `2d42164` (NuGet 5.0.0).
Used by [PLC-Monitor](https://github.com/nsuarez75/PLC-Monitor) as a separate, replaceable assembly
(`S7CommPlusDriver.dll`). Changes live on branch `plcmonitor`.

| Date | Change |
|---|---|
| 2026-10-15 | `Legitimation/Legitimation.cs`: any non-zero `ReturnValue` is access denied (the `Int16` cast accepted a wrong password on an S7-1517F) |
| 2026-10-15 | `S7CommPlusProtocolSession.cs`: symbol lookup skips native areas the CPU does not have (S7 timers/counters on S7-1200) instead of failing with "Could not get type info" |
| 2026-10-15 | `Properties/AssemblyInfo.cs`: `InternalsVisibleTo` for PLC-Monitor's s7-symbolic driver and its tests |
| 2026-10-15 | `S7CommPlusDriver.csproj`: `S7CommPlusIncludeOpenSslRuntimes=false` omits the native OpenSSL files |
