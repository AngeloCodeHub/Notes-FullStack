# Anaconda 建置 python 環境筆記

Anaconda 完整安裝包預設會安裝 Conda（CLI）、Anaconda GUI、及300+ package

## 案例：建立我自己的全域環境

GitHub spec-kit

1. 建立全域（global）環境並指定 python版本  
   `conda create -n myenv python=3.14`  
   此時會安裝一些預設軟體包
2. 安裝 [GitHub spec-kit](https://anaconda.org/channels/conda-forge/packages/spec-kit/overview)  
   `conda install conda-forge::spec-kit`  
   相依性也會一併安裝
3. PowerShell指令碼啟動 myenv環境  
   ```PowerShell
   # Python-Conda.ps1
   & 'C:\ProgramData\anaconda3\shell\condabin\conda-hook.ps1'
   conda activate myenv
   ```

## conda 指令

- 查看環境
  `conda info --envs`
- 確認當前環境
  `conda info --envs`
- 列出安裝的軟體包
  `conda list`

## Packages管理

- update所有可升級套件  
  `conda update --all`

## 筆記

- [Chat－套件管理與依賴關係](https://www.perplexity.ai/search/dang-shi-yong-condaguan-li-pyt-Qto3CXErRc658FWpK5MZwg)
- pkgs是提供下載好的程式硬連結用，刪了也沒關係（但沒有必要，因為是硬連結），要刪的話使用 conda clean
- anaconda不會動到windows環境變數，一切以它自有script動態新增環境變數
- anaconda可視為完整生態，幾乎開發使用的工具指令都有內建（如cURL）
- anaconda安裝後約5G
- 大部分Windows可執行檔位置，active env會將此目錄引入  
  `C:\ProgramData\anaconda3\Library\bin`  
  `C:\ProgramData\anaconda3\Scripts`
- 移除 anaconda只會移除system（programdata），家目錄會殘留
- system安裝目錄  
  `C:\ProgramData\anaconda3`
- Global安裝目錄  
  `C:\Users\AngeloHu\.conda`
- conda要使用PowerShell 5.1，否則 intellisense不能用並且會產生其他不相容問題
- base環境的packages不要動，由anaconda管理
- ~/.conda/pkgs 裡面是什麼?可以刪除或管理嗎?  
  `conda clean --all`
- 升級 conda  
  `$ conda update --name base conda`
- [Anaconda denpendencies ORG](https://anaconda.org/)
- Anaconda (base) 虛擬環境建構在system，安裝依賴必須提高權限（conda與gui都要），位置如下  
  `C:\ProgramData\anaconda3`  
  新建的環境才是在使用者家目錄，位置如下  
  `C:\Users\user\.conda\envs\myenv`
- 創建環境如果使用 clone，預設會複製 python 主程式與全部軟體包
- conda 虛擬環境只是動態載入環境變數
- packages來源（channel）：conda內建、conda-forge（Anaconda.org）、pip

## VSCode 插件

- VSCode python插件：[Python - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.python)  
  安裝此插件會一併安裝（啟用）以下三個插件
  1. [Pylance - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
  2. [Python Debugger - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.debugpy)
  3. [Python Environments - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-python-envs)
- [Python Environments - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-python-envs)

## FAQ

- 新建myenv是否可使用base的packages?  
  A：[巢狀 active](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#nested-activation)
- 環境與依賴可不可以像 npm 安裝在專案目錄?  
  A：[Specifying a location for an environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#specifying-a-location-for-an-environment)
