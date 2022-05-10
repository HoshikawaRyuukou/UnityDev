“Your architectures should tell readers about the system, not about the frameworks you used in your system” — Robert C. Martin
這種架構不是專注於框架和工具，而是專注於應用程序的業務邏輯。它是獨立於框架的（盡可能地）。
這意味著無論您使用哪個數據庫、開發框架、UI 或外部服務，應用程序的實體和業務邏輯都將始終保持不變。



好的架構必須做到關注的點分離 / 分層 - 依賴倒置

依賴關係只能向內，外圈變化不能影響內圈

實體層 Entities
包含構建我們應用程序的所有業務實體。
可以是簡單的資料型態或是帶有方法的物件 

用例層 Use Cases
包含我們的應用程序支持的所有業務場景。

介面轉接層 Interface Adapters
資料格式的轉換(最適合use case層 <-> 最適合外部(Web或資料庫))

框架和驅動層 Frameworks and Drivers
UIs / 資料庫

跨邊界

總結
1.將軟體分層
2.外層依賴內層
