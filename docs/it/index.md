# Snaplogic IT

- Workday-Parlance.Operator_Assist
    - REST GET to Workday Report Parlance.Operator_Assist
    - output= 1 txt file sftp to Parlance server.
    - task= (pipeline, sftp) scheduled Daily at 6PM
    - vendor support=
    - v1.1.0

- IDAUTO-PerceptiveContent
    - SQL Server Select, Update to INOW Perceptive Content DB
    - output= email to admin, change to database
    - task= (pipeline) scheduled Weekly, Friday at 12PM
    - v1.1.0

- Google-AD
    - Captures Google Worksheet data (802.1x keyboardless devices) and uses AD Create Entry snap to create account
    - output= no output, change to AD
    - task= scheduled pipeline running hourly
    - v1.0.0

- Google-AD.Password
    - Captures Google Worksheet data (802.1x keyboardless devices) and uses AD Update Entry snap to update password for each CN
    - output= no output, change to AD
    - task= NA (child pipeline of Google.AD)
    - v1.0.0

- Banner-LDAP
    * Banner-LDAP.JSON
        - initiates integration chain
        - v1.0.0
    * Banner.course-LDAP.course-LDAP
        - Captures Banner course data to do LDAP course group write
        - v1.0.0
    * Banner.course.timestamp-file.timestamp.JSON
        - Writes SLDB file for date compare
        - v1.0.0
    * Banner.enrollment-ldap.enrollment-parent.JSON
        - Captures, transforms Banner enrollment data for LDAP write (child)
        - v1.0.0
    * Banner.enrollment-ldap.enrollment-child.JSON
        - Using parent upstream dataset, wrte to LDAP
        - v1.0.0
    * Banner.timestamps-Banner.enrollment.cleanup.JSON
        - Cleans up Banner enrollment data after scheduled integration
        - v1.0.0
    * LDAP.semester.cleanup-parent.JSON
        - Semester end clean up trigger pipeline
        - v1.0.0
    * LDAP.semester.cleanup-child.JSON
        - Semester end clean up child pipeline
        - v1.0.0

- Banner-DeliveredReports.ChosenNameReport current version v1.3.1
    - Oracle Select
    - output= email, MS Excel spreadsheet
    - task= (pipeline) scheduled daily, 6:30AM
    - v1.3.0

- Banner-DeliveredReports.StatusChangeReport current version v1.2.1
    - Oracle Select
    - output= email, MS Excel spreadsheet
    - task= (pipeline) scheduled daily, 6PM
    - v1.2.0
    
- Banner-EMC_Warehouse-Fall
    - Captures data for a fall semester in data warehouse
    - Oracle Select
    - task= (pipeline) scheduled weekly April - December
    - v1.0.0
    
- Banner-EMC_Warehouse-Spring
    - Captures data for a spring semester in data warehouse
    - Oracle Select
    - task= (pipeline) scheduled weekly November - Jun
    - v1.0.0

- Workday.AuditLog-Splunk.WorkdayIndex
    - Workday Production Audit Data to Splunk for ISO
    - Using Workday REST API and HTTP Event Collector service from Splunk
    - task= (pipeline) triggered via HTTP req from workday-splunk.py on dataintegration02
    - v1.0.2

- Workday-DeliveredReports.NewHireEmail
    - REST GET to Workday Report 'New Hire Summary w/ Email'
    - output= email, MS Excel spreadsheet
    - task= (pipeline) scheduled monthly, 1st of every month at 6:30AM
    - v1.0.0

- Workday-Mailman.Email_Distribution_List
    - REST GET to Workday Report 'All Active Employees Distribution List Source for Integration'
    - output= .dis file to MailMan
    - task= (pipeline) scheduled dailiy 6:00AM
    - v1.6.0

- Workday-Mailman.Emeriti_Email_Distribution_List
    - REST GET to Workday Report 'Emeriti Distribution List for Integration'
    - output= .dis file to MailMan
    - task= (pipeline) scheduled dailiy 6:00AM
    - v1.2.0

- Banner.Audit-Splunk.INDEX
    - Oracle EXECUTE on sql to pull the audit data from DBMS table
    - output= Splunk data
    - task= (pipeline) scheduled hourly
    - v1.0.1

- Banner-DeliveredReports.OverEnrolledCLS
    - Oracle Select
    - output= email, MS Excel spreadsheet
    - task= (pipeline) scheduled daily, 6:00 AM
    - v2.0.0
	
- Workday.Emeriti-Communications
    - Rest GET of Workday Custom Report: Retired_Emeriti_for_Integration_for_Communications
    - output= csv to drop/cmsbios
    - task= (pipeline) scheduled Fridays, 6:00 PM
    - v1.1.0
	
- Workday.WorkerEducation-Communications
    - Rest GET of Workday Custom Report: Worker_Education_for_Communications
    - output= csv to drop/cmsbios
    - task= (pipeline) scheduled Fridays, 6:00 PM
    - v1.0.2
	
- Workday|Banner-Directory
    - Rest GET of Workday Custom Report: Directory Data-Employees
    - Rest GET of Workday Custom Report: Directory Data-Contingent Workers    
    - Rest GET of Workday Custom Report: Emeriti Distribution List for Integration
    - Oracle procedure InsertVCDIRStu
    - output= write to Oracle table DAIES.VCDIR
    - task= (pipeline) scheduled Every day, every hour from 8:00AM to 5:00PM
    - v1.0.1

- Banner|Workday-Adobe-DeliveredReport
    - Rest GET of Workday Custum Report: Emeriti Distribution List for Integration
    - Oracle Execute
    - output= csv
    - task= (pipeline) runs ad hoc
    - v1.0.0

- Banner.PostOfficeData-PostOffice.SharedFolder
    - Oracle Select
    - output= CSV,  winfile02 write
    - task= (pipeline) scheduled daily, 11:30PM
    - v1.1.0

- Workday.CommitteeMembership-Communications
    - Rest GET of Workday Custom Report: All_Committees_Membership_List_for_Integration
    - output= txt to drop/committees
    - task= (pipeline) scheduled Weekdays, 3:00 AM
    - v1.0.1

- Workday.Committees-Communications
    - Rest GET of Workday Custom Report: All_Committee_Names_and_Definitions_for_Integration
    - output= txt to drop/committees
    - task= (pipeline) scheduled Weekdays, 3:00 AM
    - v1.0.0
    
- Banner.Workday-SolarWinds
    - Oracle Select
    - REST GET of Workday Custom Report: Active_Employee_Worker_Location_for_Integration
    - output= CSV,  \\BBuniversal03\solarwinds\
    - task= (pipeline) scheduled Sunday - Friday, every hour
    - v1.3.1

- Banner.Workday-SendSuite
    - Oracle Select
    - REST GET of Workday Custom Report: Active_Employee_Worker_Location_for_Integration
    - output= Text Tab Delimited files (2), smb://SENDSUITE02.vassar.edu/Import/
    - task= (pipeline) Daily 6am
    - v1.0.0
	
- CallManager.Extension-Workday.Worker
    - Oracle Insert 
    - Oracle procedure DAIES.IDENTIFY_PHONE_CHANGES
	- MS SQL join with IDAUTO data
    - AXL API GET of extension data from CallManager
    - output= Workday Web Service Contact Change
    - task= (pipeline) scheduled Weekdays, 3:00 AM
    - v1.0.1

- Workday.Banner-BannerApps-BuildingDisList
    - Oracle Select
    - REST GET to Workday Report 'Active_Employee_Worker_Location_for_Integration'
    - output= .dis files to MailMan
    - task= (pipeline) scheduled dailiy 6:00AM
    - v1.1.0
	
- Banner.Moodle-CreateCoures
    - Oracle procedure upd_ap_exam_codes
    - output= .xlsx to DeanOfStudies Shared Drive
    - task= (pipeline) scheduled Every day, 9:00PM
    - v1.0.2

- Banner.Workday-Banner.Namesdata
    - Oracle Select
    - REST GET to Workday Report 'Active_Employee_Worker_Location_for_Integration'
    - output= Oracle INSERT brioserver.namesdata
    - task= scheduled daily 6am
    - v1.0.0

- Banner.Workday-PostofficeData
    - Oracle Select
    - REST GET to Workday Report 'Active_and_Inactive_Employee_Worker_Location_for_Integration'
    - Output= Oracle INSERT bn.postoffice_rebuild & bn.postoffice
    - task= scheduled daily 11:30pm
    - v1.2.0

- Workday-GoogleDrive.HealthCheck - DEPRECATED and replace by Workday-MySQL.HealthCheck
    - REST GET to Workday Reports 'All Worker Time Off - Daily Health Questionnaire' & 'Submitted Unsubmitted Reported Time Blocks for a Worker with In Out Time - Revised'
    - Output= Write to Google Spreadsheet - Snaplogic-HealthCheck
    - task= scheduled daily 12:30am
    - v1.0.0

- Workday-MySQL.HealthCheck 
    - REST GET to Workday Reports 'All Worker Time Off - Daily Health Questionnaire' & 'Submitted Unsubmitted Reported Time Blocks for a Worker with In Out Time - Revised'
    - Output= Write to MySQL tables
    - task= scheduled daily 12:30am
    - v1.0.1

- Banner-DeliveredReports.RoomChange 
    - Oracle select
    - Output= Excel file emailed 
    - task= scheduled daily 6:30am
    - v1.0.0

- Workday.Digital_Signage
    - REST Get to Workday Report 'Active_Employee_Worker_Location_for_Integration'
    - Output= Excel file to 'signcms01/dsfiles/content/directories/'
    - task= scheduled daily 6am
    - V1.0.1

- Banner.Student-DeliveredReport-General_Student_Exception_Reports
    - Oracle select
    - Output= Excel files emailed
    - Task= scheduled daily 6am
    - V1.2.0

- Banner-DeliveredReports.MealChange 
    - Oracle select
    - Output= Excel file emailed 
    - task= scheduled daily 6:30am
    - v1.0.0

- Banner-DeliveredReports.MealPlanCompare 
    - Oracle select
    - Output= Excel file emailed 
    - task= scheduled weekly Fridays @ 6:00am
    - v1.0.0

- Banner-PrereQ.SCAPREQ-SSAPREQ
    - Oracle select, delete, insert
    - task= scheduled daily @ 4:00am
    - v1.0.0
