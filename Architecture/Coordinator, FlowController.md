# Coordinator / FlowController

## 目的
>協調器/流控制器可以讓我們從表示層組件(ViewController/ViewModel/Presenter)中移除應用程序導航的工作，幫助它們更易於管理和更可重用，並可以在需要時調整應用程序的流程。

以下表示層組件均以 VC 表示
以下Coordinator / FlowController均以 Flow 表示

隨著應用程式的擴展，免不了必須在 VC 之間做導航。最簡單的方式便是以強引用的方式讓 VC 知道另一個 VC，但這裡的緊耦合是應該避免的，
登入VC應該知道忘記密碼VC嗎?那是他的責任嗎? 沒有忘記密碼的操作就沒辦法做登入的操作嗎? 並不是，所以內聚力不夠強，應該把登入與忘記密碼的關係抽出到另一個類中   

登入View上有一個 忘記密碼按鈕
當這個按鈕被點擊時代表的應該是 忘記密碼按鈕被點了/想執行忘記密碼 而不是 執行忘記密碼的相關操作
忘記密碼 在登入View只是個字串

VC 在應用程序中獨立存在時效果最佳，不知道它們在您的應用程序流中的位置，甚至不知道它們是流的一部分。
這不僅有助於使您的代碼更易於測試和推理，而且還允許您更輕鬆地在應用程序的其他地方重用視圖控制器。

因此導入 Flow負責 序列的操作

## 實作


## Reference
[How to use the coordinator pattern in iOS apps](https://www.hackingwithswift.com/articles/71/how-to-use-the-coordinator-pattern-in-ios-apps)
