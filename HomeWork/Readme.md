## การบ้าน Sequence Diagram

ข้อ 1 Web Register

Code
``
@startuml
actor First #Green
participant Register 
participant Database
First->Register:Enter Your Detail
Register->Register:Validate Detail
Register->Database:Send User Deatail
Database->Database:Insert User Deatil
Database->First :Return  Result To User
@enduml
``


ข้อ 2 ตู้น้ำหยอดเหรียญ

Code
``
@startuml
actor First #Green
participant "Water cooler" 
participant "KeyPad Select Water" 
participant system 

First->"Water cooler":Insert Coin
First->"KeyPad Select Water":Select Water
First->"Water cooler":Cancel Insert Coin
"Water cooler" -> system:Send Water Drink
"Water cooler" -> First:Send Water Drink
system<-"KeyPad Select Water":Send Data
system<-system:Process Data
system->"Water cooler" :Send Data
@enduml
``

ข้อ 3 ซื้อของผ่านเว็บ

Code
``
@startuml
actor Customer #Green
participant Webpage 
participant Database 
participant Seller

Customer->Webpage:Register
Customer->Webpage:Select Product
Database<-Webpage:Send Product Data
Database<-Database:Send Process Data
Database->Webpage:Valid
Seller<-Webpage:Send Data Customer and Product
Seller->Customer:Send Email To User
@enduml
``

ข้อ 4 Update BookBank Machine

Code
``
@startuml
actor Customer #Green
participant "Machine update bookbank" 
participant Database 

Customer->"Machine update bookbank":Insert BookBank
Database<-"Machine update bookbank":Search Data
Database->"Machine update bookbank":Return Data
"Machine update bookbank"->"Machine update bookbank":Print BookBank
"Machine update bookbank"->Customer:Update Finish
@enduml
``

ข้อ 5 แสกนบาโค้ดเช็คราคาสินค้า

Code
``
@startuml
actor Customer #Green
participant "Scan barcode"
participant Database 

Customer->"Scan barcode":Check Price
Database<-"Scan barcode":Search Data
Database<-Database:Search :Process
"Scan barcode"<-Database:Search :Send Data Price
Customer<-"Scan barcode":Tell Price Product
@enduml
``


