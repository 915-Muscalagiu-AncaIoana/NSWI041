@startuml

class Faculty{
    - name : string
    - type : string
    - address : string
    - students : list 
    - studyProgrammes : list
    - enrollment : list 
    - teachers : list
    
    string getName()
    string getType()
    string getAddress()
    void setName(newName : string)
    void setType(newType : string)
    void setAddress(address : string)
    list getStudent()
    list getStudyProgrammes()
    list getTeachers()
    list getEnrollments()
    void addStudent(student : Student)
    void removeStudent(id : integer)
    void updateStudent(id : integer , newStudent : Student)
    void addTeacher(teacher : Teacher)
    void removeTeacher(id : integer)
    void updateTeacher(id : integer , newTeacher : Teacher)
    void addStudyProgramme(studyProgramme: StudyProgramme)
    void removeStudyProgramme(id : integer)
    void updateStudyProgramme(id : integer , newStudyProgramme : StudyProgramme)
    void addEnrollment(enrollment : Enrollment)
    void removeEnrollment(id : integer)
    void updateEnrollment(id : integer, newEnrollment : Enrollment)
    list getAllStudentsFromStudyProgramme(studyProgramme : StudyProgramme)
    StudyProgramme getStudyProgrammeOfStudent(student : Student)
}

class Enrollment {
    - id : integer
    - student : Student
    - studyProgramme : StudyProgramme
    - date : datetime

    integer getId()
    Student getStudent()
    StudyProgramme getStudyProgramme()
    datetime getDate()
    void setDate(newDate : datetime)
}

class StudyProgramme {
    - id : integer
    - name : string
    - capacity : integer
    - subjects : list
    - subjectEnrollments : list
    - applications : list
    - teachings: list

    integer getId()
    string getName()
    integer getCapacity()
    void setCapacity(newCapacity : integer)
    void setName(newName : string)
    void addSubjectEnrollments(subjectEnrollments : SubjectEnrollments)
    void removeSubjectEnrollments(id : integer)
    void updateSubjectEnrollments(id : integer, newSubjectEnrollments : subjectEnrollments)
    void addSubject(subject : Subject)
    void removeSubject(id : integer)
    void updateSubject(id : integer, newSubject : Subject)
    void addApplication(application : Application)
    void removeApplication(id : integer)
    void addTeaching(teaching : Teaching)
    void removeTeaching(id : integer)
    void updateTeaching(id : integer, newTeaching : Teaching)
    list getTeachersOfSubject(subject : Subject)
    list getSubjectsByTeacher(teacher : Teacher)
    list getSubjectsOfStudent(student : Student)
    list getStudentsOfSubject(subject : Subject)

}

class Teaching {
    - id : integer
    - teacher : Teacher
    - subject : Subject

    integer getId()
    Teacher getTeacher()
    Subject getSubject()
}

class Teacher {
    - id : integer
    - name : string
    - email : string
    
    integer getId()
    string getName()
    string getEmail()
    void setName(newName : string)
    void setEmail(newEmail : string)
    void gradeRegularExam(regularExam : RegularExam)
    void gradeThesis(thesisProject : ThesisProject)
    void gradeFinalExam(finalExam : FinalExam)
}

class Student {
    - id : integer
    - name : string
    - email : string
    - phone : string
    - yearOfStudy : integer
    - thesisProject : ThesisProject
    finalExam : FinalExam
    regularExams : list

    integer getId()
    string getName()
    string getEmail()
    string getPhone()
    string getYearOfStudy()
    void setName(newName : string)
    void setEmail(newEmail : string)
    void setPhone(newPhone : string)
    void setYearOfStudy(newYear : integer)
    void takeFinalExam(finalExam : FinalExam)
    void takeRegularExam(regularExam : RegularExam)
    void presentThesisProject(thesisProject : ThesisProject)
    list getAllRegularExams()
    Result getResultForRegularExam(regularExam : RegularExam)
    Result getResultForFinalExam(finalExam : FinalExam)
    Result getResultForThesis(thesisProject : ThesisProject)
    list getAllResultsOfRegularExams()
}

class SubjectEnrollment{
    - id : integer
    - subject : Subject
    - student : Student
    - date : datetime

    integer getId()
    Subject getSubject()
    Student getStudent()  
    datetime getDate()
    void setDate(newDate : datetime)
}

class Application {
    - id : integer
    - admissionExam : AdmissionExam
    - enrollee : Enrollee
    - date : datetime

    integer getId()
    Enrollee getEnrollee()
    AdmissionExam getAdmissionExam()
    boolean hasEnrolleePassed()
    double getAdmissionExamGrade()
    datetime getDate()
    void setDate(newDate : datetime)
}

class AdmissionExam {
    - id: integer
    - date : datetime
    - place : string
    - duration : integer
    - subject : string
    - grade : double

    integer getId()
    datetime getDate()
    string getPlace()
    integer getDurationInHours()
    string getSubject()
    double getGrade()
    void setGrade(newGrade : double)
    void setDate(newDate : datetime)
    void setPlace(newPlace : string)
    void setDuration(newDuration : integer)
    boolean isPassed()
}

class Enrollee {
    - id : integer
    - name : string
    - birthDate : datetime
    - phone : string
    - email : string
    - address : string

    integer getId()
    string getName()
    datetime getBirthDate()
    string getPhone()
    string getEmail()
    string getAddress()
    void setName(newName : string)
    void setEmail(newEmail : string)
    void setPhone(newPhone : string)
    void setAddress(newAddress : string)
 
}

class Subject {
    - id : integer
    - name : string
    - description : string
    - results : list
    
    integer getId()
    string getName()
    void setName(newName : string)
    string getDescription()
    void setDescription(newDescription : string)
    list getResults()
    string getStatisticReport()
}

class Result {
    - id : integer
    - teacher : Teacher
    - grade : double

    integer getId()
    double getGrade()
    teacher getTeacher()
    double setGrade()
}

class ThesisProject {
    - id : integer
    - supervisor : Teacher
    - result : Result
    - subject : string
    - description : string
    - yearOfDefence : int
    - yearOfAssignment : int

    integer getId()
    double getResultGrade()
    Result getResult()
    Teacher getSupervisor()
    integer getYearOfAssignment()
    integer getYearOfDefence(
    void changeSupervisor(teacher : Teacher)
    void changeSubject(string : subject)
    void changeDescription(string : description)
    void setResult(result : Result)
}

class FinalExam {
    - id : integer
    - date : datetime
    - resultslist : list
    - place : string
    
    datetime getDate()
    Result getResult()
    string getPlace()
    double getAverageResult()
    list getResultsList()
    Teacher getTeachers()
    void addResult(result : Result)
    void removeResult(id : integer)
    void setPlace(newPlace : string)
    void changeDate(newDate : datetime)
}

class RegularExam {
    - id : integer
    - date : datetime
    - result : Result
    - subject : Subject
    - place : string

    integer getId()
    datetime getDate()
    Result getResult()
    string getPlace()
    double getResultGrade()
    Teacher getTeacher()
    Subject getSubject()
    void setResult(result : Result)
    void changeDate(newDate : datetime)
    void changePlace(newPlace : string)
}

class University{
    - name : string
    - faculties : list
    - accounts : list

    string getName()
    void setName(name : string)
    list getFaculties()
    list getAccounts()
    void addFaculty(faculty : Faculty)
    void removeFaculty(name : string)
    void updateFaculty(name : string , newFaculty : Faculty)
    void addAccount(account : Account)
    void removeAccount(id : integer)
    void updateStudent(id : integer , newAccount : Account)
    list getTeacherAccounts()
    list getStudentAccounts()
    list getEnrolleeAccounts()
}

class Account {
    - id : integer
    - username : string
    - password : string
    - type : string 
    
    integer getId()
    string getUsername()
    string getType()
    string getPassword()
    void setUsername(newUsername : string)
    void setPssword(newPassword : string)
    void setType(newType : string)
}

University "1" --* "many" Faculty
University "1" --* "many" Account
Faculty "1" --* "many" Student
Faculty "1" --* "many" Enrollment
Faculty "1" --* "many" StudyProgramme
StudyProgramme "1" --* "many" Teaching
Faculty "1" --o "many" Teacher
Enrollment "many" --* "1" Student
Enrollment "many" --* "1" StudyProgramme
StudyProgramme "1" --* "many" Subject
StudyProgramme "1" --* "many" SubjectEnrollment
StudyProgramme "1"--* "many" Application
SubjectEnrollment "many" --* "1" Subject
SubjectEnrollment "many" --* "1" Student
Teaching "many" --* "1" Teacher
Teaching "many" --* "1" Subject
Student "1" --* "1" ThesisProject
Student "1" --* "1" FinalExam
Student "1" --* "many" RegularExam
RegularExam "1" --o "1" Subject
RegularExam "1" --* "1" Result
FinalExam "1" --* "many" Result
ThesisProject "1" --* "many" Result 
Subject "1" --* "many" Result
Result "1" --o "a" Teacher
Application "1" --o "1" Enrollee
Application "1" --* "1" AdmissionExam


@enduml

