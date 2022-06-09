# Coordinator / FlowController

## 目的
>協調器/流控制器可以讓我們從表示層組件(ViewController/ViewModel/Presenter)中移除應用程序導航的工作，幫助它們更易於管理和更可重用，並可以在需要時調整應用程序的流程。

以下表示層組件均以 VC 表示

隨著應用程式的擴展，免不了必須在 VC 之間做導航。最簡單的方式便是以強引用的方式讓 VC 知道另一個 VC，但這裡的緊耦合是應該避免的，
VC真的應該知道另一個 VC嗎?那是他的責任嗎?隨著功能增加


## 實作


## Reference
[How to use the coordinator pattern in iOS apps](https://www.hackingwithswift.com/articles/71/how-to-use-the-coordinator-pattern-in-ios-apps)
