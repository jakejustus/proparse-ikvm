# proparse-ikvm

IKVM'ized version of [Proparse](https://github.com/jakejustus/proparse)

## How to use from PowerShell

```powershell
[Reflection.Assembly]::LoadFile("C:\Users\xxx\path\to\IKVM.OpenJDK.Core.dll")
[Reflection.Assembly]::LoadFile("C:\Users\xxx\path\to\IKVM.OpenJDK.Util.dll")
[Reflection.Assembly]::LoadFile("C:\Users\xxx\path\to\IKVM.OpenJDK.Text.dll")
[Reflection.Assembly]::LoadFile("C:\Users\xxx\path\to\IKVM.Runtime.dll")
[Reflection.Assembly]::LoadFile("C:\Users\xxx\path\to\proparse-net-1.0.1-SNAPSHOT.dll")

$pscSettings = new-object org.prorefactor.refactor.settings.ProgressSettings
$ppSettings = new-object org.prorefactor.refactor.settings.ProparseSettings
$schema = new-object org.prorefactor.core.schema.Schema("path/to/db.schema")
$session = new-object org.prorefactor.refactor.RefactorSession($pscSettings, $ppSettings, $schema)

$unit = new-object org.prorefactor.treeparser.ParseUnit("path/to/procedure.p", $session)
$unit.treeParser01()
$unit.getTopNode().toStringFullText()
```

## How to use from ABL

Left as an exercise to the reader. Please note that the "legacy" API won't probably work correctly due to numerous API changes.
