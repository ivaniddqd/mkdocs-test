# Vacation Manager

For creating applications for vacations, time off and relocation

## Description

Front and back for production and development are deployed on a virtual machine on GCP

## Infrastructure

Database - GCP Cloud SQL "postgresSQL"

The infrastructure of the service is implemented using Docker. The `docker-compose.yml` file is located on the server outside the front and back directories, where it is used to launch the service.
- qa_backend - the main volume from the qa_backend folder and the /home/jenkins/resources/vocation-manager.p12 file
- qa_frontend - the main volume from the qa_frontend/build folder
- database - with settings
- Ngxinx_proxy_manager(app) - (ports 80, 81, 443) nginx that proxies requests to the front/back

## Solution

A script has been implemented to retain the last (n=5) versions of old build JAR files. When the 6th build is created, the script removes the oldest version (1st in sequence), moves the current build to the folder with old versions, and sets the newly built one as the current build.
The script is located at /home/jenkins/script.sh. The folder containing the old versions is at /home/jenkins/old_qa_backend_builds.

