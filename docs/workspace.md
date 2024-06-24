# Workspace

## Description

The backend is deployed in Docker along with the database, while the frontend is hosted using GCP Cloud Storage and a load balancer. Additionally, NGINX is set up locally on servers to act as a proxy server.

## Another heading

more text

## Helpful tips

??? note "If it is necessary to increase the size of the uploaded file..."

    To increase the size of the uploaded file, you need to configure the NGINX configuration file 
    hat is installed locally (not in a container!) on the server. The configuration involves adding 
    the `client_max_body_size` parameter. Additionally, developers should change the file size check 
    settings on the frontend.