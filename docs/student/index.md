# snaplogic-student

- Banner-Symplicity.CSM *decommissioned
    - REST GET endpoint: https://dataintegration01.vassar.edu/api/vassarapi/v1/student?vendor=symplicity-csm
    - output= csv file transfer to vendor's sftp site
    - task= scheduled Monday's at 1am
    - vendor support= 	vassar-csm-support@symplicity.com
    - version: v1.0.1

- Banner.Student-JoinHandShake
    - REST GET endpoint: https://appconnect.vassar.edu/api/vassarapi/v1/student?vendor=joinhandshake
    - output= csv file transfer to vendor's s3
    - task= scheduled Monday's at 5am
    - vendor support= 	support@joinhandshake.com
    - version: v1.4.0

- Banner-Maxient
    - REST GET endpoint: https://appconnect.vassar.edu/api/vassarapi/v1/student?vendor=maxient
    - Oracle SP= DAIES.get_maxient_dataset; DAIES.get_maxient_dataset__schedule
    - output= 2 txt files to drop server. Data may eventually go directly to vendor sftp if "Constant" Snap output could be 1 binary document for "File Writer" Snap
    - task= (pipeline) scheduled Daily at 11PM; (sftp) scheduled daily at 10AM
    - vendor support= support@maxient.com
    - version: v1.0.4

- Banner-MBS.Renters
    - REST GET endpoint: https://appconnect.vassar.edu/api/vassarapi/v1/student
    - REST GET endpoint: https://appconnect.vassar.edu/api/vassarapi/v1/employee
    - Oracle SP= DAIES.get_student_dataset; DAIES.get_employee_dataset
    - output= 1 txt file to MBS Vendor sftp server.
    - task= (pipeline) scheduled Daily at 7AM;
    - vendor support= AGray@mbsbooks.com
    - version: v1.0.1

- Banner-MBS.Courses
    - REST GET endpoint: https://appconnect.vassar.edu/api/vassarapi/v1/course
    - Oracle SP= DAIES.get_course_dataset
    - output= 1 txt file to MBS Vendor sftp server.
    - task= (pipeline) scheduled Daily at 7AM;
    - vendor support= AGray@mbsbooks.com
    - version: v1.1.2

- Banner-NelNet.StudentChoice
    - REST GET endpoint: https://appconnect.vassar.edu/api/vassarapi/v1/student/account/refund
    - Oracle SP= DAIES.get_sturefund_dataset
    - output= 1 xml file written to NelNet SFTP representing refund data entered in Banner the previous day
    - task= scheduled daily at 1am
    - vendor support= help@nelnet.net
    - version: v1.0.0

- NelNet.Student-Banner.Email
    - SFTP File Reader to capture StudentChoice Response XML
    - output= 1 csv attached email to stuaccounts@vassar.edu containing refund response data
    - task= scheduled daily 5am
    - vendor support= help@nelnet.net
    - version: v1.0.2

- NelNet.ReturnFund-Banner.Email
    - SFTP File Reader to capture StudentChoice Response XML
    - output= 1 csv attached email to stuaccounts@vassar.edu containing refund response data
    - task= scheduled daily 5am
    - vendor support= help@nelnet.net
    - version: v1.1.1

- Acalog.Banner.Parent and .Child
    - SFTP File Reader to identify and load files with course changes from DigArc server
    - output=csv file imported to staging table
    - Oracle SP= BN.ACALOG_BANNER_COURSE_IMPORT
    - task= 1st, 8th, 15th, 22nd and 29th at 8am
    - vendor support= support@acalog.com
    - version: v1.1.1

- Banner.TerraDotta
    - Oracle Execute to select student/employee data from Banner
    - output=csv file written to TerraDotta server for import
    - task= everyday at 2:30am
    - version: v1.0.0

- PowerFAIDs-Banner
    - Generic JDBC - Select to select student financial aid data from PowerFAIDs mySQL table
    - output=data inserted into summary Oracle table 
    - Oracle SP= DAIES.UPDATE_JOBX_FA_SUMMARY
    - task= daily 6:30pm
    - version: v1.0.1

- Banner-AIM-ClassList
    - Oracle Execute to identify active classes for current and future semesters
    - output=csv file written to AIM server for import
    - task= daily 2am
    - vendor support= sales@accessiblelearning.com
    - version: v1.0.0

- Banner-AIM-StudentGPAs
    - SFTP File Reader to identify active students who require accomodations
    - Oracle Execute to compare active student list with Banner GPA data
    - output=csv file written to AIM server for import
    - task= daily 2am
    - vendor support= sales@accessiblelearning.com
    - version: v1.0.0

- Banner-AIM-StudentCourses
    - SFTP File Reader to identify active students who require accomodations
    - Oracle Execute to compare active student list with student course Banner data
    - output=csv file written to AIM server for import
    - task= daily 2am
    - vendor support= sales@accessiblelearning.com
    - version: v1.0.0

- Banner-AIM-StudentInfo
    - SFTP File Reader to identify active students who require accomodations
    - Oracle Execute to compare active student list with student Banner data
    - output=csv file written to AIM server for import
    - task= daily 2am
    - vendor support= sales@accessiblelearning.com
    - version: v1.0.0
