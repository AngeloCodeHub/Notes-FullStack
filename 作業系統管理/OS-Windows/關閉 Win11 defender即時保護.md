<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# 關閉 Windows 11 defender 的 病毒防護的即時保護?

要關閉 Windows 11 Defender 的病毒防護即時保護，可以按下列步驟操作，分成「暫時關閉」和「永久關閉」兩種方式：

### 暫時關閉即時保護操作步驟

1. 在開始選單搜尋並開啟「Windows 安全性」。[^1_1][^1_2][^1_3]
2. 點選左側「病毒與威脅防護」。[^1_4][^1_5][^1_1]
3. 在主畫面找到「病毒與威脅防護設定」，點擊「管理設定」。[^1_2][^1_6][^1_1]
4. 將「即時保護」的開關切換為「關閉」。[^1_3][^1_5][^1_1]

此方法關閉後，下次重開機或系統更新時會自動開啟，僅適合暫時用途。[^1_2][^1_3]

### 永久關閉 Defender 即時保護

#### 方法一：使用群組原則編輯器（僅限專業版／企業版）

1. 同時按下 Win + R 鍵，輸入 `gpedit.msc`，開啟本地群組原則編輯器。[^1_7][^1_1][^1_3]
2. 導航至「電腦設定 → 管理範本 → Windows 元件 → Microsoft Defender 防毒軟體」。[^1_8][^1_1][^1_3]
3. 雙擊「關閉 Microsoft Defender 防毒軟體」選項。
4. 設定為「已啟用」，按下「確定」。[^1_1][^1_3][^1_8]
5. 重新啟動電腦。[^1_3][^1_1]

#### 方法二：使用登錄檔（所有 Windows 版本）

1. 按下 Win + R 鍵，輸入 `regedit`，打開登錄檔編輯器。[^1_9][^1_10][^1_1]
2. 導航至 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` 路徑。[^1_9][^1_1]
3. 新增 DWORD (32 位元) 值，名稱為 `DisableAntiSpyware`，值設為 1。[^1_10][^1_1][^1_9]
4. 重新啟動電腦。[^1_1][^1_9]

這些方法可視您需求選用，提醒永久關閉防護有資安風險，建議僅在必要或有替代防毒方案的情況使用。[^1_2][^1_3][^1_1]
<span style="display:none">[^1_11][^1_12][^1_13][^1_14][^1_15]</span>
***Angelo備註：使用registry方法，要將防竄改關掉才會生效，要回復只要刪除機碼***
<div align="center">⁂</div>

[^1_1]: https://jamespolik.pixnet.net/blog/post/346965835

[^1_2]: https://tw.easeus.com/backup-recovery/windows-11-defender-disable.html

[^1_3]: https://www.ubackup.com/tw/windows-11/turn-off-windows-defender-windows-11.html

[^1_4]: https://www.myai168.com/tw/article/index?sn=11181

[^1_5]: https://www.mobile01.com/topicdetail.php?f=300\&t=6913695

[^1_6]: https://support.microsoft.com/zh-tw/windows/防毒與反惡意程式碼軟體-常見問題-31f2a46e-fad6-b713-45cf-b9db579973e6

[^1_7]: https://www.dell.com/support/kbdoc/zh-tw/000108754/如何使用群組原則編輯器在-windows-中永久停用-windows-defender

[^1_8]: https://blog.csdn.net/COCO56/article/details/128613164

[^1_9]: https://adersaytech.com/kb-article/disable-windows-defender.html

[^1_10]: https://www.reddit.com/r/WindowsHelp/comments/1cyojiz/windows_11_pro_how_to_permanently_disable/

[^1_11]: https://www.youtube.com/watch?v=sM9HD7iLszY

[^1_12]: https://www.reddit.com/r/WindowsHelp/comments/1hzsshp/win11_24h2_defender_keeps_enabling_itself_over/

[^1_13]: https://ofeyhong.pixnet.net/blog/post/222758271

[^1_14]: https://learn.microsoft.com/zh-tw/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus

[^1_15]: https://www.youtube.com/watch?v=vKZvmam6aqE

