# CV Builder

For creating CVs in corporate style

## Description

Frontend, backend, and database for production and development are deployed on a virtual machine on GCP

## Infrastructure

Directory Files:
- `agreement.txt`: This file records the decision on whether to move the new build to replace the current one or not (to verify if the build is executed correctly and will work).
- `archive-builds-from-pipeline-noreleased/`: Folder containing unreleased builds (those that run if the variable is set to “no”).
- `new-build-from-pipeline/`: Folder where the freshly built pipeline build is moved. Depending on the agreement, the files in this directory will either be moved to noreleased or replace the current frontend in `/var/www/cv-builder-resume`.
- `release.sh`: The script that performs the actions.
- `resume-old-builds/`: Folder where former current releases are sent.

## Frontend

## Backend

## Database

## Solution

??? note "How the Frontend Pipeline Launch Works..."

    The pipeline launch is implemented with manual approval following best practices. A variable 
    named prod_agreement is introduced. By default, it is set to “no”. “No” means that the new 
    build will not be moved to the folder with the currently running build. First, run with “no” 
    to ensure everything goes smoothly and the pipeline doesn’t break (the code is correct). 
    After that, manually run the pipeline with the variable set to “yes” so that the newly 
    created build becomes the current one.

## Helpful tips

??? note "If the password for the mailing mailbox changes..."

    If the password for the mailing mailbox changes, you need to update the EMAIL_PASS 
    variable located in the .env file on the server. Additionally, on the dev server, this file 
    contains the LM_EMAIL, TM_EMAIL, and PM_EMAIL variables, which specify the email addresses
    to which mailings from the dev server will be sent.
