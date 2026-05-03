# opticore-erd## 📊 OptiCore ERD

```mermaid
erDiagram
  AcademicPeriod ||--o{ ScheduleEntry : term
  AcademicPeriod ||--o{ ScheduleLoadJustification : load_review
  AcademicPeriod ||--o| DoiScheduleFinalization : publish
  AcademicPeriod ||--o{ ScheduleChangeRequest : change_req

  College ||--o{ Program : has
  College ||--o{ Room : optional_scope
  College ||--o{ Users : staff_or_student
  College ||--o{ ScheduleLoadJustification : per_college_term
  College ||--o{ WorkflowInboxMessage : inbox
  College ||--o{ AccessRequest : access
  College ||--o{ AuditLog : scope
  College ||--o{ ScheduleChangeRequest : routing

  Program ||--o{ Section : sections
  Program ||--o{ Subject : catalog
  Program ||--o{ Users : chairman
  Program ||--o{ StudentProfile : enrollment

  Section ||--o{ ScheduleEntry : class
  Section ||--o{ StudentProfile : roster
  Section ||--o{ FacultyProfile : advisory

  Users ||--|| FacultyProfile : faculty
  Users ||--|| StudentProfile : student
  Users ||--o{ ScheduleEntry : teaches
  Users ||--o{ Notification : receives
  Users ||--o{ ScheduleChangeRequest : reviewer
  Users ||--o{ WorkflowInboxMessage : sender
  Users ||--o{ AccessRequest : requester
  Users ||--o{ AuditLog : actor
  Users ||--o{ ScheduleLoadJustification : author
  Users ||--o| DoiScheduleFinalization : decidedBy

  Subject ||--o{ ScheduleEntry : offering
  Room ||--o{ ScheduleEntry : location

  ScheduleEntry ||--o{ ScheduleChangeRequest : cascade
```
