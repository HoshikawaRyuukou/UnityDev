# Coordinator / FlowController

## 目的
> 協調器/流控制器的核心責任是處理應用程序不同屏幕之間的流邏輯，使我們的表現層組件(ViewController/ViewModel/Presenter)得以移除應用程序導航的工作，使表現層組件更易於管理和重用。

## 問題
- 以下 ViewController 均以 VC 表示
- 以下 Coordinator / FlowController 均以 Flow 表示

隨著應用程式的擴展，免不了必須在 VC 之間做導航。最簡單的方式便是以強引用的方式讓 VC 知道另一個 VC，但 
- LoginVC 應該知道 ForgetPasswardVC 嗎?      
  當然可以知道 ForgetPasswardVC，但這樣他未來勢必會知道更多，比方 LogOutVC / SwitchUserVC，將導致 LoginVC 的責任將變得不穩定。

- LoginVC 的責任是什麼? 沒有忘記密碼的操作就沒辦法做登入的操作嗎?    
  LoginVC 的責任是登入，與忘記密碼並無關係，兩者間內聚力不夠強，應該把登入與忘記密碼的關係抽出到另一個類中。   

因此導入 Flow 負責流邏輯，它負責從 VC 導航到另一個單獨 VC，VC 不知道它們在應用程序流中的位置，甚至不知道它們是流的一部分。
回到實際的畫面思考產生強引用的原因。LoginView上有一個忘記密碼按鈕，這是個令人誤會的點，當這個按鈕被點擊時代表的應該是?
1. 執行忘記密碼操作 (透過其他 VC )
2. 請求忘記密碼操作 (僅發出請求)

那再想想 忘記密碼操作之前必須先看個廣告 / 操作後必須填個問卷    
- 選項1這時要執行什麼? 廣告/問卷又要在何處安排，必須對 LoginVC 修改
- 選項2並沒有發生變化仍然是發出請求

如果想讓用戶進行忘記密碼操作，請讓 Flow 顯示一個忘記密碼頁面。Flow 清楚有那些東西應該被適當地呈現(廣告->忘記密碼->問卷)。



## 實作
### 規則
- Flow 有一個啟動方法 Start()，裡面封裝了Flow對 VC的控制，必要的話也能有 Stop()
- 可以擁有 Child Flow，

### 例子
這裡是以 MVVM 做例子，表示層組件將出現 ViewController/ViewModel (VC/VM)，這裡用觀察者模式，也能使用委派

AppFlow.Start()     
-> 訂閱 LoginFlow.ForgetPasswardRequested => ForgetPasswardFlow.Start() {訂閱 ForgetPasswardFlow.Completed => LoginFlow.Show()  }   
-> LoginFlow.Start()  

LoginFlow.Start()     
-> LoginVC.Show() -> UerVM.ForgetPassward()   
-> 觸發 ForgetPasswardRequested    

ForgetPasswardFlow.Start()   
-> ForgetPasswardVC.Show() -> UerVM.ResetPassward(...)    
-> 觸發 Completed   


## Reference
[An introduction to coordinators](https://malinsundberg.com/architectures/2017/08/29/coordinators)
[How to use the coordinator pattern in iOS apps](https://www.hackingwithswift.com/articles/71/how-to-use-the-coordinator-pattern-in-ios-apps)

