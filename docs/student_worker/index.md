# Snaplogic Workday Student Employment
Pipelines related to Workday, Banner, Student Employment

- Workday - Hire Into Workday
    - version: v1.9.3
    - author: romanovsky@vassar.edu. domcneil@vassar.edu
    - launch-type: schedule [daily 4:30am EST; 5:00am EST]
    - SME: Student Employment / Human Resources
    - desc: This integration takes hires from JobX and creates, as needed, pre-hire, hire records.  It also handled secondary/additional
    job hiring.  Post-Hire, key student attributes are updated in Workday.  These include, DOB, SSN, Banner IDs, contact info, etc.

- Workday.Payroll-PowerFAIDs
    - version: v1.0.0
    - author: domcneil@vassar.edu
    - launch-type: schedule [weekly, Friday 5:00pm EST]
    - SME: Student Employment / Payroll
    - desc: This integration pulls Payroll information, filtered for the Student pay group, aggregates and delivers to PowerFAIDs import directory.
	
- WD - Student Worker Update
    - v1.1.3

- WD - Terminate Student
    - v1.0.3

- WD - Work Study Limits to Workday
    - v1.1.1

- WD - Work Study Payments to Banner
    - v1.0.0

- WD - Workday Position to JobX Position (Parent)
    - v1.2.0

- WD - Workday Position to JobX Position (Child)
    - v1.1.0
