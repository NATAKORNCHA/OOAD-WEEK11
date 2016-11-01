# OOAD-WEEK11 Homework
State Diagram

* ภาพที่ 1 State Diagram การทำงานของลิฟต์

Code

 ```
@startuml

title Lift
state "Move Up" as MoveUp 
state "Move Down" as MoveDown 
[*] -r-> Idel : Turn On
Idel -u-> [*] : Turn Off
Idel -r-> MoveUp : Want Up/Go Up
Idel -d-> MoveDown : Want Down/Go Down
MoveUp -d-> Reach : Desired Floor Reached
Reach --> Idel : Floor > 1/Go Down
MoveDown -r-> Reach : Floor <> & Desired Floor Reached
MoveDown -u-> Idel : Floor = 1

@enduml
 ```
diagram

<img src="https://github.com/NATAKORNCHA/OOAD-WEEK11/blob/master/Homework/State%20Diagram1.png?raw=true">



* ภาพที่ 2 State Diagram Turn On- Off (เปิด-ปิดเครื่อง) 

Code

 ```
@startuml

title Turn On- Off 

[*] -r-> Off 
Off : Do/Shut Down the power
Off -r-> On : Switch is turned On
On : Do/Turn On the Computer
On -u-> Boot : Switch On Complete
Boot : Do/Loading Opertion System
Boot -l-> Ready : Booting Complete
Ready : Do/Waiting for Instructions
Ready -l-> [*]


@enduml
 ```
diagram

<img src="https://github.com/NATAKORNCHA/OOAD-WEEK11/blob/master/Homework/State%20Diagram2.png?raw=true">



* ภาพที่ 3 State Diagram for PIN Entry

Code

 ```
@startuml

title State Diagram for PIN Entry

state "Wait for PIN" as WaitforPIN
state "Access to Account" as AccesstoAccount
state " 1st Try" as  1stTry
state "2nd Try" as 2ndTry
state "3rd Try" as 3rdTry

[*] -r-> WaitforPIN : Card Inserted
WaitforPIN -r-> 1stTry : Enter PIN
 1stTry -r-> 2ndTry : PIN not OK
 1stTry --> AccesstoAccount : PIN OK
 2ndTry-r-> 3rdTry : PIN not OK
 2ndTry --> AccesstoAccount : PIN OK
3rdTry  --> [*] : PIN not OK
3rdTry --> AccesstoAccount : PIN OK

@enduml
 ```
diagram

<img src="https://github.com/NATAKORNCHA/OOAD-WEEK11/blob/master/Homework/State%20Diagram3.png?raw=true">


* ภาพที่ 4 State Diagram Shopping Online

Code

 ```
@startuml

title State Diagram for Shopping Online

state "Summary and Cost" as SummaryandCost
[*] --> Empty 
Empty --> Shopping : Add Item
Shopping --> Empty : Remove last Item
Shopping --> Shopping : Remove Item
Shopping --> SummaryandCost : Check Out
Shopping --> Shopping : Add Item
SummaryandCost -->  Shopping : Not OK
SummaryandCost --> Payment : OK
Payment -d-> [*]

@enduml
 ```
diagram

<img src="https://github.com/NATAKORNCHA/OOAD-WEEK11/blob/master/Homework/State%20Diagram4.png?raw=true">


* ภาพที่ 5 State Diagram Play Game

Code

 ```
@startuml

title State Diagram for Play Game

state "Win State" as WinState
state "Loss State" as LossState
state "New Game" as NewGame

[*] --> NewGame 
NewGame --> WinState 
WinState --> LossSatae : Lost
LossState --> Winstate: Win
LossState --> [*] : End Game
WinState -->  [*] 
@enduml
 ```
diagram

<img src="https://github.com/NATAKORNCHA/OOAD-WEEK11/blob/master/Homework/State%20Diagram5.png?raw=true">

## OOAD-WEEK11 Homework
# Activity Diagram

* ภาพที่ 1 Activity Diagram ของ ATM

Code

 ```
@startuml

(*) --> "New User"
-->"Enter Details"
-->"Enter User Name"

if "Exists" then
-->[No] "Account Created"
--> (*)
else
-->[Yes] "Another User Name"
-r->"Enter User Name"
endif

@enduml
 ```
diagram

<img src="https://github.com/NATAKORNCHA/OOAD-WEEK11/blob/master/Homework/Activity%20Diagram1.png?raw=true">


* ภาพที่ 2 Activity Diagram การ Login

Code

 ```
@startuml

(*) --> "Login"
-->"Enter User name And Password"

if "Vaild" then
-->[Yes] "Search Item"
--> (*)
else
----->[No] "Enter User name And Password"
endif

@enduml
 ```
diagram

<img src="https://github.com/NATAKORNCHA/OOAD-WEEK11/blob/master/Homework/Activity%20Diagram2.png?raw=true">


* ภาพที่ 3 Activity Diagram ต้องการอาหาร

Code

 ```
@startuml

(*) --> === S1 ===
-->"Make Coffee" 
 === S1 === --> "Make Breakfast"
--> === S2 ===
 "Make Coffee" --> === S2 ===
 if "Want more Coffee" then
-->[No] "Satisfied"
--> (*)
else
-->[Yes] "Make Coffee"
endif

@enduml
 ```
diagram

<img src="https://github.com/NATAKORNCHA/OOAD-WEEK11/blob/master/Homework/Activity%20Diagram3.png?raw=true">



* ภาพที่ 4 Activity Diagram Online Banking system

Code

 ```
@startuml

(*) --> "LoginID and Password"

if "Right Password" then
-->[Yes] "Select Operation Transaction"
--> "Select View Account Balance"
--> "View Account Balance"
--> "Print Account Balance Sheet"
--> (*)
else
----->[Wrong Password] "Enter User name And Password"
if "Reenter Password" then
-->[Yes] "LoginID and Password"
else
----->[Yes] "Exit"
-->(*)
endif
endif

@enduml
 ```
diagram

<img src="http://www.plantuml.com/plantuml/img/VP3B2W8n34Nt_OhGbGhp2wAY2q5my8c8Yz29CuKnbJQYds_dWI_KJTeafysz6GH1BvTJgLIdruKawOEUkTpoT0p86QGOmjNvJ2jbZw0NDY_aMGGfY5LyjDzHE81UKab6O7ucZs8TmyeZ1pJLNQlwynRPMBh2q1XtOO4HbiY6Mk9FA_KsrZvwi2o8f26Y1qLbe9WabQojTvm_z4Q54nRoi0unC9u8XcyUQuj4DVFJvFVrl4vjkCdDDgfgKPpPOnlL89xLoky0">



* ภาพที่ 5 Activity Diagram ชำระเงินอาหาร

Code

 ```
@startuml

(*) --> "New User"
--> === S1 ===
-->"Sent Invoice"
-->"Receive Payment"
=== S1 === --> "Dispatch goods"

"Receive Payment" -->  === S2 ===
"Dispatch goods" -->  === S2 ===
--> Close Order
--> (*)

@enduml
 ```
diagram

<img src="http://www.plantuml.com/plantuml/img/SoWkIImgAStDuUBIqD9KqDMrKr3oIorN22rEBLBY0d5jRMqLWWr158Yh59oQLwBWcLUMdvcS2bQW59IQd9fPbgeGa5YP2vHKuaBeW9ZdabbSa5YIdA6Gdf-VKgp4nOMX1QmEOfCHs2PqFHWAG7pddFpYL0N_efJK8Z0Vw04kBeVKl1IGTm00">
