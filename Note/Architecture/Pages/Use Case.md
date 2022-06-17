Clean架構的分層界定了邊界，帶來了能分工的好處，因為不必知道 上下界具體做了甚麼 表示層只在乎DTO 
要給Usecase的Input與 Usecase給出Output

用例驅動 / Usecase應該做一件完整的事，完整到什麼程度?

-----------------

想一下今天是負責寫表示層，希望看到何種狀況

Scenario 1
要處理的是角色支援技能釋放的呈現效果，並且有次數限制

1. 
你看到Usecase層有兩個用例，
- ReleaseSkill(id) => skillObject
- CountDownSkillCount => (isVaild, count)
好的，先執行CountDownSkillCount檢查能否釋放，在ReleaseSkill(id)
還行，把各自的輸出呈現就完事了，用例組合的邏輯還算簡單

2.
你看到Usecase層有1個抽象用例
- IReleaseSkill(id) => (isVaild, count, skillObject)
好的，執行ReleaseSkillWithCounter，把輸出呈現就完事了

-------------------

Scenario 2
要處理的是角色支援技能釋放的呈現效果，並且有次數限制
*但角色有無敵Buff則無視次數限制 (無敵Buff的呈現不再此處，這裡只管技能釋放)

1. 
你看到Usecase層有3個用例，
- ReleaseSkill(id) => skillObject
- CountDownSkillCount => (isVaild, count)
- CheckInvincible => isVaild

好的，先執行CheckInvincible不成立後再執行CountDownSkillCount檢查能否釋放，再ReleaseSkill(id)
開始越想越不對勁，Conrtoller/Presenter 在做的事怎麼一直變
不應該是 Conrtoller發出執行請求/Presenter執行回覆就完事了嗎?
Conrtoller不是發個trigger而已嗎?? 我還要處理前置條件? 但User這邊只有一個(可釋放)Button?

2.
你看到Usecase層有1個抽象用例
- IReleaseSkill(id) => (isVaild, count, skillObject)
好的不用改 

-------------------

有感受到差異了嗎?
3個用例沒有把責任做完(玩家請求釋放技能)
組合玩家請求的責任落在表示層

-------------------

甚麼你說什麼 
Conrtoller這邊有很多參數可以影響決定Skill
這樣 IReleaseSkillFactory背後會不會類別爆炸? 
可能會吧 沒規劃的話?
但那跟你 Conrtoller有甚麼關係，把參數傳過來就沒你的事了

-------------------

竟然被畫面變化影響了內圈決策，不行吧

內圈被影響了沒錯，但不是因為畫面變化，是需求變化，畫面也是被需求影響
內外圈保護的情況是在，需求不變，內圈需求變化，外面也高機率要變

-------------------

有時必須在可重用和單一職責中做個權衡
現在在看可重用這件事上會更謹慎 (更多的時候是設計不良)
寫不同層的時候真的應該切換一下腦袋/避免使用上帝視角

