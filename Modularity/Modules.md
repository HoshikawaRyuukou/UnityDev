App / Feature / Core / Common / Shared Modules

## Modules
這使我們能夠將項目分解為更小的離散單元以管理複雜性。

### App-Module
此模塊了解整個應用程序，所有功能模塊都將包含在此(這裡不討論 Dynamic feature modules (DFM))。
它的職責是初始化應用程序組件，並作為獨立功能模塊之間的通信媒介。

### Feature-Module
此模塊是應用程序中特定功能的容器。理想情況下，它應該是小型的且獨立的。

### Core-Module


### Common-Module


### Shared-Module



### 模塊化的好處
- 構建更快：並行構建/只構建已更改的模塊。
- 關注點分離：功能模塊進行封裝。
