# Snaplogic Alumni
pipelines associated with Alumni data and applications

- Banner-EverTrue.GivingTree
    - REST GET endpoint: https://appconnect.vassar.edu/api/vassarapi/v1/alumni?vendor=evertrue
    - output= csv file transfer to vendor's sftp site
    - task= scheduled Daily - 3AM
    - vendor support= support@evertrue.com 
    - v1.3.0

- GSuite.PrincipalProspects-Banner.Alumni
    - output= INSERT into Oracle table adw.ASP_CON_PRIN_PROS
    - task= scheduled
    - v1.0.0

- GSuite.TrusteePipeline-Banner.Alumni
    - output= INSERT into Oracle table adw.TRUSTEE_PIPELINE
    - task= scheduled
    - v1.0.0

- Slate-thankQ.Volunteers
    - output= INSERT into SQL Server table dbo.relationship, dbo.relationshiparchive / DELETE SQL Server table dbo.relationship
    - task= scheduled Daily 10:30pm
    - v1.0.0

- thankQ-Slate.Volunteers
    - output= Drop .csv file sftp://ft.technolutions.net:22/incoming/BannerVolunteers.csv
    - task = scheduled Daily 11pm
    - v1.0.0