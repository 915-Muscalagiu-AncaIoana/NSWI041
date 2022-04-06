@startuml
partition Enrolee {
(*top) -right-> "Request application form" 
 -down-> "Complete personal information"
 -down-> "Submit application form"
}
partition System {
 -down-> "Check all mandatory fields"
if "" then
  -->[Valid form] "Check format of fields"
       if "" then
       -->[Wrong format fields] "Notify user error" 
       else
       -> [Valid form] "Record personal information"
       -down-> (*) 
       endif
else
  ->[Incomplete form] "Notify user error" 
  -up-> "Complete personal information"
endif
}

@enduml