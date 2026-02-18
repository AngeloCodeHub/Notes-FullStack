
1. diskmgmt.msc 創建一個 VHDX磁碟
2. [使用 Linux 初始化與格式化並創建 Partition](https://www.perplexity.ai/search/zai-ubuntu-linuxxia-ru-he-jian-GtzM95F6RhCHPTvaVWDusQ)
3. `sudo lsblk -f` 會看到一個空的磁碟
4. 建立GPT磁碟→建立分割區→ 寫入 
   ```Bash
   sudo fdisk /dev/sdd
   ```
5. 分割區格式化為 EXT4  
   ```Bash
   sudo mkfs.ext4 /dev/sdb1
   ```
6. 使用 WSL 指令掛載（需要提高權限）  
   ```PowerShell
   wsl --mount --vhd \path\to\file.vhdx --partition 1 --name VHD_Ext
   ```
