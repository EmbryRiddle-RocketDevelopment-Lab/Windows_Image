# Windows_Image

```
$downloadsPath = (New-Object -ComObject Shell.Application).Namespace('shell:Downloads').Self.Path + "/RDL_Windows.json"
irm "https://raw.githubusercontent.com/EmbryRiddle-RocketDevelopment-Lab/Windows_Image/refs/heads/main/RDL_Windows.json" -OutFile $downloadsPath

iex "& { $(irm https://christitus.com/win) } -Config $downloadsPath -Run"


$downloadsPath = (New-Object -ComObject Shell.Application).Namespace('shell:Local AppData').Self.Path + "/Temp/Win11Debloat/Win11Debloat-master/CustomAppsList"
irm "https://raw.githubusercontent.com/EmbryRiddle-RocketDevelopment-Lab/Windows_Image/refs/heads/main/CustomAppsList" -OutFile $downloadsPath

& ([scriptblock]::Create((irm "https://debloat.raphi.re/"))) -Silent -RemoveAppsCustom
```
