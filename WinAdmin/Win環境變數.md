# 環境變數

[Chat－備份環境 Windows 環境變數](https://chatgpt.com/g/g-ZpZUQbCxM-vs-code-copilot/c/6922e25f-1a4c-8323-8aa7-0ea6995c9bec)

## 記事

- %APPDATA% 此種寫法只在進階系統設定或檔案總管有效，PowerShell指令碼無效
- 環境變數Terminal關掉就會消失，否則都會在同一Powershell Session都會記得
- [MS-Learn Windows 文件](https://learn.microsoft.com/en-us/windows/deployment/usmt/usmt-recognized-environment-variables)
- [Perplexity](https://www.perplexity.ai/search/microsoft-windows-li-c-windows-rGrLc9yjTEaT.SUWaYH5hA)
- [如何在 Windows PowerShell 中設置 PATH 環境變數](https://www.delftstack.com/zh-tw/howto/powershell/set-the-path-environment-variable-in-powershell/)
- [Powershell about_Environment_Variables](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_environment_variables)
- [MS-Learn setx 指令](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/setx)
- [pwsh-dotenv](https://gitlab.com/kamiyonanayo/pwsh-dotenv)
- [Setting Environment Variables in PowerShell: A Practical Guide](https://configu.com/blog/setting-environment-variables-in-powershell-a-practical-guide/)
- 在 PowerShell 指令加入暫時的環境變數
  ```PowerShell
  $env:PGHOST="localhost"
	$env:PGDATABASE="postgres"
	$env:PGPORT="54322"
	$env:PGUSER="postgres"
	$env:PATH += ";SomeRandomPath" 
	$Env:PATH = "%LOCALAPPDATA%;$Env:PATH"
	$Env:PATH = $Env:PATH+";%LOCALAPPDATA%"
	$Env:PATH = $Env:PATH+";%APPDATA%"
  ```

## 討論串

- [Setting Windows PowerShell environment variables - Stack Overflow](https://stackoverflow.com/questions/714877/setting-windows-powershell-environment-variables)
- [Adding path permanently to windows using powershell doesn't appear to work - Stack Overflow](https://stackoverflow.com/questions/69236623/adding-path-permanently-to-windows-using-powershell-doesnt-appear-to-work)

## 取得環境變數

```PowerShell
# GUI
sysdm.cpl

# 調用.NET
write-Host ([Environment]::GetEnvironmentVariable('PATH'))

# 取得環境變數，方法 1
Set-Location env:
Get-ChildItem path | Get-Content
Get-Variable

# 取得環境變數，方法 2
cd env:
Get-ChildItem

# 使用環境變數
cd $env:windir

# 查看環境變數所有內容，後面點點點切斷
Get-ChildItem path | Get-Content
write-output $Env:PATH
```

## 設定環境變數

```PowerShell
Set-Variable

# 永久修改指令（會覆蓋請謹慎使用）。可以使用%變數方式
setx.exe
```
