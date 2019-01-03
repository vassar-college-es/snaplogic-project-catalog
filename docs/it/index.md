# Snaplogic IT

- Banner-Parlance current version v1.0.1
    - REST GET endpoint: https://appconnect.vassar.edu/api/vassarapi/v1/employee
    - Oracle SP= DAIES.get_employee_dataset
    - output= 1 txt file sftp to Parlance server.
    - task= (pipeline, sftp) scheduled Daily at 6PM
    - vendor support=
    - v1.0.1

- Banner-PerceptiveContent current version v1.1.0
    - Oracle Select, Update on Banner, Perceptive Content DB
    - output= no output, change to database
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

- Banner-DeliveredReports.ChosenNameReport current version v1.1.0
    - Oracle Select
    - output= email, MS Excel spreadsheet
    - task= (pipeline) scheduled daily, 6:30AM
    - v1.1.0

- Banner-DeliveredReports.StatusChangeReport current version v1.0.0
    - Oracle Select
    - output= email, MS Excel spreadsheet
    - task= (pipeline) scheduled daily, 6:30AM
    - v1.0.0
