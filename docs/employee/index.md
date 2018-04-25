# Snaplogic Employee
pipelines associated with Employee data and applications

- Banner-FourWinds.DigitalSignage
    - REST GET endpoint: https://appconnect.vassar.edu/api/vassarapi/v1/employee/directory
    - output= csv file transfer to internal Windows server
    - task= scheduled Daily - 3AM
    - vendor support= ledinnebeil@vassar.edu
    - v1.0.0

- Workday.Worker-RaveAlert
    - Workday RaaS: https://services1.myworkday.com/ccx/service/customreport2/vassar/romanovsky/RPT_MJR_Vassar_Alert_System?format=simplexml
    - v1.0.0
    - Drop CSV to drop.vassar.edu:22
    - Daily 7am
