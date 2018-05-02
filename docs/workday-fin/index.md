# Snaplogic Workday Finance
Pipelines related to Workday Finance

- WD - Banner.Gift to Workday.AHBT.Gift
    - version: v1.1.6
    - author: romanovsky@vassar.edu
    - launch-type: scheduled [11:15pm daily]
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
    - v.1.1.3

- WD - Banner.StudentCharges to Workday.AcccountJournals
    - v.1.0.6

- WD - JPM.PCard-Workday.SubmitAcctJournal
    - v.1.1.0

- WD - Unpost-Acct-Journals
    - v.1.0.0

- WD - FixDate-JPM.PCard-Workday.SubmitAcctJournal
    - v.1.0.0
