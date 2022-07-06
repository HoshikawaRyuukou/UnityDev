## MVP (Model-View-Presenter)
### 入門
- [MVP Pattern](https://deltatimer.com/258/mvp-pattern-part-1-passive-view)
- [Android-MVP](https://github.com/Tuong-Nguyen/PreparationEduLog/wiki/Android-MVP)
> 作者總結了各個部分的工作內容，其中**Navigation被放在View層**(這部分各方有很多種討論)
> - 因為我使用**Passive View**，基本上裡面只有呈現邏輯，不會有控制邏輯在這出現(Navigation我視為控制邏輯)
> - 使用中介者模式來對場景做導流
> - [給畫面流一個家](https://github.com/HoshikawaRyuukou/UnityDev/wiki/Self%E2%80%90Architecture#給畫面流一個家)
- [A Brief Summary of thoughts on Clean Architecture and MVP](https://dev.to/wahibhaq/a-brief-summary-of-thoughts-on-clean-architecture-and-mvp-48h9)
<br>

## MVVM（Model-View-ViewModel）
與 MVP 最大的不同是 ViewModel 不知道 View 的存在。這允許 ViewModel 純粹管理狀態，而 View 只需要訂閱該狀態並反映它。

### Model
- 域(Domain)層成員 (Usecase/Service)

### View
- 與使用者互動的元件

### ViewModel
- 作為 Model 與 View 的中介
- 與 Model 互動，但不曉得 View 的存在，但提供狀態讓 View 觀察
- 將業務邏輯得到的資料轉換成畫面所需的格式

### Binder


## MVI (Model-View-Intent)
- [Model-View-Intent](https://hannesdorfmann.com/android/mosby3-mvi-1/)


<!-- 將一個段落隱藏看不見
https://www.toptal.com/android/android-apps-mvvm-with-clean-architecture
https://cmmobile.gitbook.io/androidbook/xin-ren-xun-lian/jia-gou
-->
