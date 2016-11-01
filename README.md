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
