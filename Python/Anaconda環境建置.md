# Anaconda 建置 python 環境筆記

Anaconda 完整安裝包預設會安裝 Conda（CLI）、Anaconda GUI、及300+ package

## conda 指令

- 查看環境
  `conda info --envs`
- 確認當前環境
  `conda info --envs`
- 列出安裝的軟體包
  `conda list`

## 使用筆記

- [Anaconda denpendencies ORG](https://anaconda.org/)
- Anaconda (base) 虛擬環境建構在全域，安裝依賴必須提高權限（conda與gui都要），位置如下
  `C:\ProgramData\anaconda3`
  新建的環境才是在使用者家目錄，位置如下
  `C:\Users\user\.conda\envs\myenv`
- VSCode python插件：[Python - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
  安裝此插件會一併安裝（啟用）以下三個插件
  1. [Pylance - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
  2. [Python Debugger - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.debugpy)
  3. [Python Environments - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-python-envs)
- [Python Environments - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-python-envs)
- 創建環境如果使用 clone，預設會複製 python 煮成是與全部軟體包
- conda 虛擬環境只是動態載入環境變數
- packages來源：conda內建、conda-forge（Anaconda.org）、pip

## FAQ

- 新環境 python 與 package是否能共用?
  A：[巢狀 active](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#nested-activation)
- 環境與依賴可不可以像 npm 安裝在專案目錄?
  A：[Specifying a location for an environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#specifying-a-location-for-an-environment)
