“Your architectures should tell readers about the system, not about the frameworks you used in your system” — Robert C. Martin    
這種架構不是專注於框架和工具，而是專注於應用程序的業務邏輯。它是獨立於框架的（盡可能地）。
這意味著無論您使用哪個數據庫、開發框架、UI 或外部服務，應用程序的實體和業務邏輯都將始終保持不變。

好的架構必須做到關注的點分離 / 分層 - 依賴倒置
依賴關係只能向內，外圈變化不能影響內圈

---------------------------------



### 實體層 Entities
包含構建我們應用程序的所有業務實體。可以是簡單的資料型態或是帶有方法的物件。


### 用例層 Use Cases
包含我們的應用程序支持的所有業務場景。    

舉個例子: 根據一周天氣狀況幫土壤施加肥料
參與對象:    
實體層: 天氣(VO) / 土壤 / 肥料

天氣 = 天氣庫.Get(日期)     
肥料 = 肥料庫.Get(天氣參數)     
肥料.Apply(土壤)     

### 介面轉接層 Interface Adapters
資料格式的轉換(最適合use case層 <-> 最適合外部(Web或資料庫))

### 框架和驅動層 Frameworks and Drivers
UIs / 資料庫

### Data transfer object (DTO)



跨邊界

## 總結
1.將軟體分層
2.外層依賴內層

## 入門
* [Clean Architecture - An Introduction](https://www.dandoescode.com/blog/clean-architecture-an-introduction/)
* [Clean Architecture with .NET Core: Getting Started](https://jasontaylor.dev/clean-architecture-getting-started/)

- [架构学习之 mvp-clean](https://lilei.pro/2019/08/21/architecture-todo-mvp-clean/)
> 作者為了緩解日益增大的Presenter導入Clean架構，並著重討論Usecase
> - Clean 的核心思想是單向依賴，同心圓由外向內依賴，達到內層對外層一無所知，外層的變動不影響到內層。
> - Use Case 是業務邏輯的最小抽象單元，在我理解上就是對原先的Presenter會操作到的Model與Service做一次封裝，讓Presenter專心於View的控制。
<br>

- [再談Clean Architecture三原則](http://teddy-chen-tw.blogspot.com/2020/08/clean-architecture.html)
- [漫談 iOS 架構：從 MVC 到 VIPER，以及 Redux](https://chiahsien.github.io/post/common-ios-architecture-from-mvc-to-viper-with-redux/)
- [Clean Architecture Guide (with tested examples): Data Flow != Dependency Rule](https://proandroiddev.com/clean-architecture-data-flow-dependency-rule-615ffdd79e29)
- [Simple Clean Architecture Example for Unity](https://github.com/laicasaane/UnitySimpleCleanArchitecture)
- [Learning Architecture, MessagePipe, and VContainer by Creating a Game Requested by My Own Daughter](https://medium.com/kadinche-engineering/learning-architecture-messagepipe-and-vcontainer-by-creating-a-game-requested-by-my-own-daughter-8ee8303a718)




<!-- 將一個段落隱藏看不見
dto
https://softwareengineering.stackexchange.com/questions/373284/what-is-the-use-of-dto-instead-of-entity
-->


