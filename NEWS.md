### December 2024 - PROOF v1.2
**What's New**

- **User Interface Upgrade**: After extensive user studies, we have redesigned the user interface of PROOF to 
provide a better experience for our users throughout their research. By transitioning the framework of our 
Shiny app to bslib, the new interface will provide:
    - A cleaner and more modern-looking interface
    - Improved usability for researchers with less scrolling
    - An updated version of bootstrap for easier programming and improved performance

**Fixes**

- **Scratch Directory Requirement**: With `/fh/scratch/` becoming read-only in early December 2024, users will now be required to have an `/hpc/temp/` directory in order to use PROOF.
- **Glob Functionality**: Because `/fh/scratch/` did not allow linkages, [globbing functionality](https://github.com/openwdl/wdl/blob/wdl-1.2/SPEC.md#glob) was disabled for PROOF, but now that users are moving to `/hpc/temp/`, users can now provide glob arrays as outputs.
- **Other Minor Improvements**:
    - Expanded functionality of "zombie killer" process
    - No longer restricted to `rhino01`

### September 2024 - PROOF v1.1
**What's New**

- **Visualization Tabs**: To aid users in visualizing their analyses, we've added two new tabs to the PROOF user interface:
    - **WDL**: produces [mermaid diagrams](https://github.com/chanzuckerberg/miniwdl-viz?tab=readme-ov-file#simple) for a submitted WDL script.
    - **Viewer**: displays [input json's](https://github.com/timelyportfolio/listviewer) in a much more intuitive and collapsible way.
- **Login Persistence**: Many users have reported issues with accidentally navigating away from PROOF and having to log back in with their Fred Hutch credentials. Through a limited utilization of cookies, authentication in PROOF will now persist much longer, regardless of any navigation away from the page.
- **PROOF Analytics Dashboard**: To better assess how the Fred Hutch community is using the PROOF platform, we have created the initial framework for a Shiny-based analytics dashboard centered around PROOF.

**Fixes**

- **Cromwell Scratch Directory**: In anticipation of the [retirement](https://sciwiki.fredhutch.org/scicomputing/store_scratch/) of the `/fh/scratch/` directories of the Fred Hutch Rhino cluster, the default value for a user's Cromwell scratch directory will now be set to `/hpc/temp/` whenever possible.
- **Zombie Tasks**: On rare occassions, tasks are cancelled by the Slurm job scheduler and Cromwell has [trouble](https://github.com/broadinstitute/cromwell/issues/1499) recognizing these cancellations. This results in the task being marked as "Running" indefinitely in the "Track Jobs" tab. We have added functionality in PROOF to identify these "zombie" tasks and correctly update their status to "Cancelled".
- **Concurrent Docker Pulls**: Measures were taken to ensure that tasks running in parallel do not interfere with each other when pulling down the same Docker image.
- **Other Minor Improvements**:
    - Wording clarifications in documentation
    - Linting corrections identified by the linting GitHub Action
    - Version upgrades for underlying dependencies
    - Additional testing for improved CI/CD
    - Easier local instance creation for development purposes

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
