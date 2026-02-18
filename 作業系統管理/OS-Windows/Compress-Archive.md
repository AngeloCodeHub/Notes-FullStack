---
description: New prompt created from chat session
mode: ask
model: Auto (copilot)
---
<user>
Compress-Archive 如何加入多個準備壓縮的檔案或路徑?
</user>
<assistant>
可以。Compress-Archive 的 -Path/-LiteralPath 參數都支援多個路徑 (string[])，用逗號分隔或放進陣列即可。

- 逗號分隔:
````powershell
Compress-Archive -Path '.\_env', '.env' -DestinationPath $BckDst
````
- 陣列語法:
````powershell
Compress-Archive -Path @('.\_env', '.env', '.\conf\app.json') -DestinationPath $BckDst
````
- 含特殊字元/萬用字元請用 -LiteralPath:
````powershell
Compress-Archive -LiteralPath @('C:\Data\[raw].txt', '.\_env') -DestinationPath $BckDst
````
- 若要往已存在的 zip 追加或更新檔案，改用 -Update:
````powershell
Compress-Archive -Path '.\_env', '.env' -DestinationPath $BckDst -Update
````

將你檔案中的壓縮行修正並順便定義來源清單如下：
````powershell
# ...existing code...
$BckDst = "$env:OneDrive\EnvBackup\" + $BckName

$BckSrc = @('.\_env', '.env')
Write-Host $BckSrc
Write-Host $BckDst

Compress-Archive -Path $BckSrc -DestinationPath $BckDst
# ...existing code...
````
</assistant>