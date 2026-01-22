# Hyper-V

## Windows Server

1. 新增 Hyper-V 功能
2. 依照微軟步驟新增虛擬機器

## FAQ

- [ ] Hyper-V可否掛載實體硬碟(非VHDX)
- [ ] 檢查點的使用方式

## 其他

- [110-2網工班-Hyper-V-虛擬硬碟-實體機新增，虛擬機使用 - YouTube](https://www.youtube.com/watch?v=UmYGIxDZYtw)
- [Hyper-V documentation | Microsoft Learn](https://learn.microsoft.com/en-us/windows-server/virtualization/hyper-v/)
- 動態記憶體的效能比較差
- 虛擬機要對外連線要新增虛擬交換器，新增虛擬交換機會斷線
- [Hyper-V 3.0 實戰 :: 2013 iT 邦幫忙鐵人賽](https://ithelp.ithome.com.tw/users/20006428/ironman/522)
- [梳理一下 Windows 的 Hyper-V、Hypervisor - 知乎](https://zhuanlan.zhihu.com/p/381969738)
  ![圖示](http://www.xn--djroe106hl2fyz1bszc.online/Hyper-V/HyberVComponent.png)

## 虛擬交換器類型

- 外部 (External)：連接實體網卡，允許 VM 與實體網路、主機（Host）以及外部網際網路通訊。
- 內部 (Internal)： 僅允許 VM 與實體主機（Host）之間溝通，無法存取外部網路。
- 私有 (Private)： 僅允許 VM 之間互相通訊，與主機及外部網路完全隔離。
