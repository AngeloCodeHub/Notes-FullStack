
## 更改 SSH Port

1. 提升權限編輯 `/etc/ssh/sshd_config` 
2. 重啟ssd service
   ```Bash
   sudo service ssh restart
   sudo /etc/init.d/ssh restart
   ```

## LVM

LVM（Logical Volume Manager，邏輯磁碟管理）是Linux系統中一種彈性的硬碟管理機制，它在實體硬碟和檔案系統之間增加一層抽象層，允許系統管理員動態調整（擴展或縮小）分區大小，而無需重新格式化或關機，大大提高了磁碟空間的利用率和管理的靈活性。 

**核心概念**

- **Physical Volume (PV, 實體磁區):** 實際的硬碟、硬碟分割區或RAID陣列。
- **Volume Group (VG, 邏輯磁碟群組):** 將一個或多個PV集合起來形成一個大的儲存池。
- **Logical Volume (LV, 邏輯磁區):** 像傳統分區一樣，從VG中劃分出來的邏輯空間，可以在其上建立檔案系統。 

**LVM的優點**

- **動態調整:**
     系統運行中可無縫擴展（通常不能縮小）檔案系統大小。
- **整合:** 跨多個硬碟，將多個磁碟空間整合成一個大的儲存池。
- **命名與管理:** 方便依用途命名磁碟（如 `/dev/vg_data/lv_logs`），而非物理名稱。
- **快照:** 支援創建資料快照（需額外設定）。
- **遷移:** 方便將整個卷組遷移到另一台機器。 

**傳統分區 vs. LVM**  
傳統分區一旦建立大小固定，調整困難；而LVM則像一個儲存資源池，可以隨需從中切出邏輯卷，並在需要時擴展，使得磁碟管理更為方便和有效。

## 教學文件

- [Linux 升華：初學者的探索到專家的洞察 :: 2023 iThome 鐵人賽](https://ithelp.ithome.com.tw/users/20162250/ironman/6237)
- [Ubuntu Server documentation](https://documentation.ubuntu.com/server/)
