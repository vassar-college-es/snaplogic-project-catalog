# Snaplogic Workday HCM/Payroll
Pipelines related to Workday HCM/Payroll

- Workday - Hire Non-Student Into Banner
    - version: v1.9.0
    - author: romanovsky@vassar.edu
    - launch-type: trigger
    - SME: Human Resources
    - desc: When a new hire completes, and has approved, an I9, Workday makes an HTTP req to a Snaplogic endpoint with Hire data in the payload.  
    This data is then used to determine 1) whether the Worker does/may exist in Banner currently or needs a new Banner ID.  Worker attrbutes such
    as Name, DOB, SSN, email, job title, status are added/updated in the Banner database.  This also triggers the IAM system to provision according
    to job/status, etc.

- Workday - Non-Student Demo Into Banner
    - version: v.1.2.4
    - author: romanovsky@vassar.edu
    - launch-type: trigger
    - SME: Human Resources
    - desc: Nighty, Workday delivers to a Snaplogic endpoint, Worker changes from the day.  These changes include job, job status, DOB, SSN, etc.  This is
    most important for account deprovisioning from a Worker termination.

- WD - Update VASR Email (WD)
    - version: v.1.2.0
    - author: romanovsky@vassar.edu
    - launch-type: scheduled [daily 11:45pm EST]    
    - SME: CIS
    - desc: This integration looks for newly created Vassar email in the Banner database (from a new hire). And updates that Worker's Workday account and Work
    Contact email with the Vassar Identity.

- WD - Additional Jobs
    - v1.3.3
    - author: romanovsky@vassar.edu
    - launch-type: scheduled [daily 8:00pm EST]
    - SME: CIS
    - desc: Worker's with additional jobs are maintained in the Banner database within table: DAIES.WD_WORKER_DATA and a null WD_PRIMARY_JOB.  This is meant for internal
    Banner reporting requirements without needing to directly connect to Workday.

- WD - GL to Banner Finance
    - v1.0.2
    - author: romanovsky@vassar.edu
    - launch-type: NA
    - SME: CIS
    - desc: DECOMMISSIONED. This was temporarily used for syncing Payroll Workday and Banner Finance

- WD - Academic Appointments to FacBios
    - v1.2.5
    - author: romanovsky@vassar.edu
    - launch-type: scheduled [daily 6:30pm EST]
    - SME: Dean Of Faculty
    - desc: This integration uses Workday RaaS to pull academic appointments and maintain the Oracle table used for the Communication / Website integration
    for Faculty Staff Listings on Academic Dept sites.  Secondary processing is done through Hyperion and drop server to move data through workflow.

- WD - Payroll Result (Fidelity) to Worker.Email
    - v1.0.0
    - author: romanovsky@vassar.edu
    - launch-type: triggered
    - SME: HCM/Beneftis Office
    - desc: This integration will received payload from Workday containing Benefit enrollee data.  It will merge this will Banner and produce a simple output file for remittance/audit tasks.
