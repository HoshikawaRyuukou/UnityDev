## MVP (Model-View-Presenter)


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







<!-- 將一個段落隱藏看不見
https://www.toptal.com/android/android-apps-mvvm-with-clean-architecture
https://cmmobile.gitbook.io/androidbook/xin-ren-xun-lian/jia-gou
-->
