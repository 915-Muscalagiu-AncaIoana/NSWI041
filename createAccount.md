@startuml
partition System {
    (*top) -right-> "Retrieve personal information"
    -down-> "Generate username"
    -right-> "Check uniqueness of username"
    if "" then
        -->[Not unique username] "Generate username using distinctive number"
        -left-> "Check uniqueness of username"
    else
        -> [Unique username] "Assign password"
        -down-> "Register account username and initial password"
        -down-> "Send credentials via email"
    endif
}
partition Enrollee {
    -down-> "Receive credential"
    -down-> (*)
}
@enduml