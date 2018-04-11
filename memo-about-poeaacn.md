# PoEAA Note

"每個模式描述了一個在我們周圍不斷重複發生的問題以及該問題解決方案的核心。這樣，你就能一次有一次的使用該方案而不必做重複勞動" 



事務腳本: transaction script

表模塊: table module

工作單元: unit of work

元數據映射: metadata mapping

表數據入口: table data gateway

事務: transaction



如果 domain model 的邏輯非常簡單而且和 DB field 十分一致 -&gt; active record

如果比較複雜 -&gt; data mapper



optimistic lock

* both can make a copy of the file and edit it
* after someone committed, code control system will reject the others commit
* conflict detection

pessimistic lock

* prevents anyone else from editing it

* conflict prevention
* reduces concurrency



isolation level

* liveness vs correctness



Unit of Work - concurrency control

Layering - Three Layer

* Presentation
* Data Source
* Domain
  

| Domain layer | Data Source | Presentation | Remark |
| :--- | :--- | :--- | :--- |
| **Transaction Script** | **Row Data Gateway** **Table Data Gateway** |  | simplest **Optimistic Offline Lock** |
| **Table Module** | **Record Sets**  **Table Data Gateway** |  | |
| **Domain Model** | **Active Record** - simple, classes close to the database  **Table Data Gateway / Row Data Gateway** - decouple  **Data Mapper** - independent, most complicated one to |  | high difficulty of learning |


# Reference
* https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420
