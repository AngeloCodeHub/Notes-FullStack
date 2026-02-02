# PowerShell on Linux

- [PowerShell differences on non-Windows platforms - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/scripting/whats-new/unix-support?view=powershell-7.5)

## 一般知識

- 設定檔位置
  ```PowerShell
  ~/.config/powershell/Microsoft.PowerShell_profile.ps1
  ```

## 安裝

- [Installing PowerShell on Ubuntu - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/scripting/install/install-ubuntu)
  PowerShell設為預設值
  ```Bash
  # 查看shell
  cat /etc/shells
  # 查看執行檔位置
  whereis pwsh
  # 切換預設值
  chsh -s /usr/bin/pwsh
  ```

## oh-my-posh

1. 安裝：[Linux | Oh My Posh](https://ohmyposh.dev/docs/installation/linux#installation)
2. 新增設定檔
   ```PowerShell
   New-Item -Path $PROFILE -Type File -Force
   ```
3. 編輯設定檔：[Change your prompt | Oh My Posh](https://ohmyposh.dev/docs/installation/prompt)
   ```PowerShell
   vi $profile
   ```
