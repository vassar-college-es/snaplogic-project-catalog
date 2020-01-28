# Snaplogic Workday Finance
Pipelines related to Workday Finance

- WD - Banner.Gift to Workday.AHBT.Gift
    - version: v1.2.0
    - author: romanovsky@vassar.edu
    - launch-type: scheduled [11:45pm daily]
    - SME: Accounting Services
    - desc: This integration pulls Gift Transactions from Banner daily, and builds a Workday request for
      the 'Submit Ad Hoc Bank Transaction' service.

- WD - Banner.Gift to Workday.Donor
    - version: v1.1.0
    - author: romanovsky@vassar.edu
    - launch-type: manual
    - SME: Accounting Services

- WD - Banner.Grant to Workday.AHBT.Grant
    - v.1.1.0

- WD - Banner.Grant to Workday.GrantCustomerInvoice
    - v.1.0.0

- WD - Sierra to Supplier Invoice Request
    - v.1.0.0

- WD - Banner.StuAcct to Workday.AHBT
    - v.1.0.0

- WD - JPM.stuPCard-Workday.SubmitAcctJournal
    - v.1.0.0

- WD - TMA.charges-Workday.SubmitAcctJournal
    - v.1.1.4
    - author: mcgowan@vassar.edu
    - launch-type: manual
    - SME: Facilities Ops

- WD - Banner.StudentCharges to Workday.AcccountJournals
    - v.1.2.0
    - author: romanovsky@vassar.edu, khahn@vassar.edu
    - launch-type: schedule [11:45pm daily]
    - SME: Accounting Services
    - desc: This integration pulls Student Charges from DAIES.gurfeed and maps/transforms for a Workday Submit_Journal_Entry request.
 
- WD - JPM.PCard-Workday.SubmitAcctJournal
    - version: v1.3.0
    - author: mcgowan@vassar.edu
    - launch-type: manual
    - SME: Procurement
    - desc: This integration loads VSA/Vehichle/Library Pcard transactions as journal entries into Workday from a 
            JPM PaymentNet mapper file

- WD - Unpost-Acct-Journals
    - v.1.0.0

- WD - FixDate-JPM.PCard-Workday.SubmitAcctJournal
    - v.1.0.0

- WD - Banner.Student-Workday.Suppliers.create
    - v.1.0.7
    - author: domcneil@vassar.edu
    - launch-type: scheduled, hourly
    - SME: Accounts Payable
    - desc: This integration creates students in Banner as suppliers in Workday

- WD - Banner.Student-Workday.Suppliers.update
    - v.1.0.4
    - author: domcneil@vassar.edu
    - launch-type: scheduled, weekly
    - SME: Accounts Payable
    - desc: This integration updates contact information for student suppliers in Workday

- WD - ThankQ to Workday Finance
    - v1.0.0
    - author: romanovsky@vassar.edu
    - launch-type: scheduled; daily
    - SME: Vassar Accounting 
    - desc: Pulls staged gift transactions from ThankQ and creates AHBT and JEs as needed based on payment type
