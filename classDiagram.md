@startuml

class Faculty{
    - name : string
    - type : string
    - address : string
}


class StudyProgramme {
    - id : integer
    - name : string
    - capacity : integer
    
}


class Teacher {
    - id : integer
    - name : string
    - email : string
}

class Student {
    - id : integer
    - name : string
    - email : string
    - phone : string
    - yearOfStudy : integer
    
}


class Application {
    - id : integer
    - date : datetime
}

class AdmissionExam {
    - id: integer
    - date : datetime
    - place : string
    - duration : integer
}

class Enrollee {
    - id : integer
    - name : string
    - birthDate : datetime
    - phone : string
    - email : string
    - address : string
 
}

class Subject {
    - id : integer
    - name : string
    - description : string
}

class Result {
    - id : integer
    - grade : double
}

class ThesisProject {
    - id : integer
    - subject : string
    - description : string
    - yearOfDefence : int
    - yearOfAssignment : int
}

class FinalExam {
    - id : integer
    - date : datetime
    - place : string
    
}

class RegularExam {
    - id : integer
    - date : datetime
    - place : string

}

class University{
    - name : string
}

class Account {
    - id : integer
    - username : string
    - password : string
    - type : string 
}

University "1" -- "many" Faculty
Faculty "1" -- "many" "StudyProgramme"
Faculty "1" -- "many" Teacher
Teacher "many" -- "many" Subject
Student "many" -- "1" StudyProgramme 
StudyProgramme "1" -- "many" Subject
StudyProgramme "1"-- "many" Application
Subject "many" -- "many" Student
Student "1" -- "1" ThesisProject
Student "1" -- "1" FinalExam
Student "1" -- "many" RegularExam
RegularExam "1" -- "1" Subject
RegularExam "1" -- "1" Result
FinalExam "1" -- "many" Result
ThesisProject "1" -- "many" Result 
Result "1" -- "1" Teacher
ThesisProject "1" -- "1" Teacher
Application "1" -- "1" Enrollee
Application "1" -- "1" AdmissionExam
Student "1" -- "1" Account
Teacher "1" -- "1" Account
Enrollee "1" -- "1" Account


@enduml

