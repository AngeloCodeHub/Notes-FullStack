# 開發環境配置

## 記事

- Windows Docker Desktop的Docker主要指令是放在另一個wsl image：docker-desktop.
  要完全分開需要創造另一個wsl並讓Docker Desktop不要連結
- Docker data disk 容量過大問題.
  [Chat](https://gemini.google.com/app/bd769e2740ff3fde)  
- [Chat－Docker與實體機原理](https://gemini.google.com/app/b4db90abb9092e93)
- [Localhost 8080 port 權限不足問題](https://chatgpt.com/share/694a81c0-0334-8006-a3fb-ae95ed8b6aee)
- [nginx forbidden 解決](https://chatgpt.com/share/694a99e1-a75c-8006-8d0c-4d9e4f64138a)
- Docker要解決的是==*軟體密集度、隔離環境* ==
  軟體密集度是盡可能有效應用電腦的資源，Docker在軟體密集度效率比VM好
- Container是共享 host os的資源
- 容器分 linux容器與windows容器，只能在與host os相同才能跑 container
  Windows能跑linux容器是因為有wsl
- Docker 容器也有自己的環境變數
- 映像檔與映像層：映像層就dockerfile裡的每一行指令，不同的映像檔與容器可共用同一個映像層.
  每一行dockerfile都一個雜湊，雜湊被破壞了就得重新執行指令
- [Docker hub 推送排查](https://gemini.google.com/app/c_98e22ccbb550b80f)
- 容器有一個可寫層，container停止時不會刪除內容

## Dockerfile
- FROM：載入映像檔，代表一個階段（映像層）

## 指令
- `docker --version`：檢查 Docker 版本。
- `docker pull <image>`：從 Docker Hub 下載映像檔。
- `docker images`：列出本地所有 Docker 映像檔。
- `docker rmi <image>`：刪除指定的 Docker 映像檔。
- `docker run <image>`：運行指定的 Docker 映像檔。
- `docker ps`：列出正在運行的容器。
- `docker stop <container>`：停止指定的容器。
- `docker exec -it <container> /bin/bash`：進入正在運行的容器。
- `docker container start 3d499f659935`：  
    啟動指定的容器。
- `docker commit ap1 myimage:latest`：  
    將容器 ap1 的變更提交為新的映像檔 myimage:latest。

## Ref
- [Docker Hub 運作原理](https://chatgpt.com/share/694a96bb-2e98-8006-9793-882d57703369)
- [如何移除 Docker Desktop 並在 Windows 與 WSL 2 改安裝 Docker Engine | The Will Will Web](https://blog.miniasp.com/post/2025/06/14/How-to-remove-Docker-Desktop-and-install-Docker-Engine-on-Windows-with-WSL-2)

## Bookmarks
- [Learn Docker in a Month of Lunches－書本範例](https://github.com/sixeyed/diamol)
- [Windows容器技術大剖析 | iThome](https://www.ithome.com.tw/news/109035)
- [微服務入門概觀 - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10290917)
- [How Docker Works｜Facebook](https://www.facebook.com/61571591542566/posts/122146426766719718)
- [Docker volumes 教學 - 從不熟到略懂 - MyApollo](https://myapollo.com.tw/blog/docker-volumes/)
- [以 Docker 為始的多種開源服務初探 :: 2021 iThome 鐵人賽](https://ithelp.ithome.com.tw/users/20129007/ironman/4153)
- [用30天來介紹和使用 Docker :: 2018 iT 邦幫忙鐵人賽](https://ithelp.ithome.com.tw/users/20103456/ironman/1320)
- [Important Docker Commands](https://www.facebook.com/codingsnow0/posts/pfbid0LWA1jJEyH95dotWr8qrZqd1PABCEEk6YkiUN6HHa8qDJS8kuzdNxnua7sHMJFoQQl)
- [Chat－容器Docker相關技術討論](https://gemini.google.com/app/82b805ad09c29967)
