# Notes from PoEAA\(WIP\)

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
| **Table Module** | **Record Sets** **Table Data Gateway** |  |  |
| **Domain Model** | **Active Record** - simple, classes close to the database **Table Data Gateway / Row Data Gateway** - decouple **Data Mapper** - independent, most complicated one to |  | high difficulty of learning |

Business logic

Application logic

Multi data mapper classes -&gt; Metadata Mapping

If the domain model is simple, use **Active Record**



### Unit of Work

Unit of Work is an object that keeps track of:

* new object created
* existing object updated or deleted

Every time create, change or delete -&gt; tell the Unit of Work

when commit, Unit of Work decide what to do

it open a transaction -&gt; Optimistic Offline Lock or PessimisticOffline Lock

and write change out to database

# Reference

* [https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420)



