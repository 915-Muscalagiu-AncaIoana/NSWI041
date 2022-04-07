@startuml
partition Enrollee {
    (*top) -down-> "LogIn"
    -down-> === S1 ===
    === S2 === -down-> "Choose faculty"
    -down-> === S3 ===
    === S4 === -down-> "Choose study programme"
    -down-> "Submit"
}
partition System {
    === S1 === -right-> "Display faculties"
    -left-> === S2 ===
    === S3 === --> "Display available study programmes"
    --> === S4 ===
    "Submit" --> "Check all mandatory fields"
    if "" then
        -->[The given fields are not chosen] "Redirect the user to choose all the fields"
    else
        ->"Submit the application"
    endif
    --> (*)
}

@enduml