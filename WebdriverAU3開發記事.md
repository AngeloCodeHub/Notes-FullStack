- google與Netflix 已登入使用者，換到不同電腦就會消失，disney可以保留
- webdriver 的元素 ID 與瀏覽器本身的 元素ID是不一樣的東西，無法共用
- 抓取元素最終是取得 ID
- WD_ElementAction
  COMPUTEDLABEL：元素的文字
  PROPERTY：元素的屬性
- 抓元素要用 copy full xpath
- AutoIT 的 @WorkingDir  *==Script程式本身位置==* ，可以在script 內使用 FileChangeDir("path") 來改變
- include 只能是純字串不能使用變數及 macro，且`#include` 指令在 AutoIt 中是**編譯時**處理的，而不是執行時。
  在腳本開始執行前就被解析，它會根據**原始的工作目錄**（通常是腳本所在目錄或 AutoIt 編譯器啟動時的目錄）來尋找檔案，FileChangeDir("path")是執行時作用，所以 對 include指令是無作用
- Powershell 是以執行ps1（$PWD）的位置決定
- Preferences 裡的 prfofile 物件就是 chromedriver Capabilities 裡的 prefs物件
- 函式 \_WD_LoadWait（）：等待網頁Load完成
  參數說明
  1. WebDirver 的 session ID
  2. Loadwait 前等待的毫秒數，有就是說開等待前停頓的毫秒
  3. 等待幾秒不符合條件 timeout，函式繼續執行
  4. 待測試
  5. 待測試
- 函式 \_WD_WaitElement（）
