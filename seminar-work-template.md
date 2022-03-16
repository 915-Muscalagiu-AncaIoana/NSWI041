# Student information system - Students
  The Students Module handles admission into the university and grading of subjects, final exams and bachelor theses.

## Functional Requirements

### User requirements

1. A person shall be able to create a new application for the university and recieve credentials of his new account.
2. An enrolee should be able to choose his admision exam and study program.
3. An administartor shall be able to manage study programs.
4. An enrolee should be able to check the results of his admission exam.
5. A student should be able to accept or decline his place at the university.
6. An administartor should be able to record the status of the student at enrollment. 
7. An administartor should be able to create statistic reports.
8. A teacher shall be able to record the subject results of students. 
9. A student should be able to see his own results at a certain subject.
10. A teacher shall be able to record the results of the final exams taken by students.
11. A student shall be able see his result at the final exam.
12. A teacher shall be able to record the subject of the bachelor theses of students.
13. A student should be able to record his bachelor thesis project.
14. A teacher shall be able to view the bachelor theses of students.

### System requirements

#### Actors

##### Enrolee

  The Enrolee applies to the university and recieves credentials for his new account. Using the account, he can choose the study program he wants to apply for and recieves the date and place of the admission exam. After taking the exam, he will be able to view his results and choose whether to enroll to the university or to decline his place. 

##### Student

The Student can view his results at subjects and final exams given by teachers. He can also record his bachelor thesis project and view the grade for it which is recorded by another teacher.

##### Administrator

The Administartor manages the study programs of the university and records the status of a student (if he accepted/declined his place before/after the deadline). He creates statisticals reports on the student success rate in each year.

##### Teacher

The Teacher records the grading for his subjects and for the final exams taken by students. He can record the subject of the bachelor theses of the students he mentors and he can view their bachelor thesis projects.

#### Use cases

[*Document here all use cases. Create a subsection for each use case diagram. If you have only one use case diagram, you do not need a special subsection*]

[*Use case diagram in PlantUML*]

```plantuml
@startuml
left to right direction

skinparam actorStyle awesome
actor Enrolee as e
actor Administrator as a
actor Student as s
actor Teacher as t


package Admission {
  usecase "Register" as UC1
  usecase "Create Account" as UC2
  usecase "Choose study program" as UC3
  usecase "Manage study programs" as UC4
  usecase "Check exam results" as UC5
  usecase "Record student status" as UC6
  usecase "Accept/decline place" as UC7
}

e --> UC1
UC1 <-- UC2 : << extends >>
e --> UC3
UC4 <-- a
e --> UC5
UC6 <-- a 
UC7 <-- UC6 : << extends >> 
e --> UC7

package Results {
  usecase "Create statistic report" as UC14
  usecase "View subject results" as UC8
  usecase "Record subject results" as UC9
  usecase "View final exam results" as UC10
  usecase "Record final exam results" as UC11
  usecase "Record bachelor thesis project" as UC12
  usecase "View bachelor thesis" as UC13
}

UC14 <-- a
UC9 <-- t
s --> UC8
UC11 <-- t
s --> UC10
s --> UC12
UC12 <-- t
UC13 <-- t

@enduml
```

To be able to embed PlantUML diagrams to Markdown code with previews in VSCode you need
* Markdown All in One extension
* PlantUML extension
* Mardown Plantuml Preview extension

Follow https://plantuml.com/

[*Describe the diagram in a short paragraph. Describe each use case from the diaram in the detail from the lecture in a separate subsection.*]

##### Register

##### Create Account

##### Choose Study Program

##### Check Exam Results

##### Accept/Decline Place

##### Record student status

##### Manage Study Program

##### Create Statistic Report

##### View Subject Results

##### Record Subject Results

##### Record Bachelor Thesis Project

##### View Bachelor Thesis

[*Use case description in the structure from the lecture.*]