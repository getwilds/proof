### June 2024 - PROOF v1.0
**What's New**
- Users can now interact with data stored in S3 buckets within WDL workflows executed in PROOF! Just make sure to have your AWS CLI credentials [established in Rhino](https://sciwiki.fredhutch.org/scicomputing/access_credentials/#configure-aws-cli) and you can use the S3 path just like any other input.
- GPU analysis is now possible via the `gpu` argument in your WDL task's runtime section! For an example, try running [this example script](https://github.com/getwilds/ww-test-workflows/blob/main/gpuMatrixMult/gpuMatrixMult.wdl) in the [ww-test-workflows](https://github.com/getwilds/ww-test-workflows) repo of the [DaSL WILDS](https://github.com/getwilds).
- Additional features have been introduced to increase transparency in terms of the functionality of PROOF:
    - New `/info` API endpoint provides details on which code base is being used.
    - Server start date and time is now available on the "PROOF Server" tab.
    - Documentation links have been added to the "Welcome" tab and automated server creation email for increased visibility.

**Fixes**
- The default location of the Apptainer cache directory has been moved from `scratch` to `/hpc/temp` to avoid previously reported linkage issues associated with `scratch`.
- PROOF's underlying WSGI server has been switched from Waitress to Gunicorn for better scalability and efficiency.
- Session persistence or "stickiness" has been added to the Shiny app to ensure users only speak to one instance at a time.
- Table entries that are longer than usual will now be abbreviated to 150 characters or less to ensure a consistent display.
- A linting GitHub action has been added to the GitHub repository for improved CI/CD. All issues identified by this linting action have also been resolved.

### February 2024 - PROOF v0.1
**What's New!**
- PROOF has now grouped together all the components for setting up and configuring your database and Cromwell server so you don’t have to manually configure each part!
- You can interact with PROOF in two improved ways when running your workflows:
    - [PROOF Shiny App](https://cromwellapp.fredhutch.org/) - an easy to use interface for accessing and configuring workflows to run on our cluster
    - Through the R clients [proofr](https://getwilds.org/proofr/) and [rcromwell](https://getwilds.org/rcromwell/) - combined these allow you to run WDL workflows on PROOF from your R console 
- We’ve made some enhancements to the way you use PROOF including:
    - Each user must login with your Fred Hutch credentials so that no one else can access or use your Cromwell server session
    - Each user can only run one Cromwell server at a time so that you don’t lose track of your workflow sessions

**Fixes**
- No fixes just yet, we’re launching our product
