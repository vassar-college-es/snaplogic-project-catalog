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