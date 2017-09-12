# Use a Docker File on Google Cloud Platform Container Image
 
## Build the Dockerfile and upload it to GCP.  Instruction found [here](https://cloud.google.com/container-builder/docs/quickstarts/dockerfile)

1.  cd to this directory `cd Image`
2.  `ls -l` - you should see Dockerfile - it will built an uploaded to GCP.

## Log in to Google Cloud

Authorize gcloud to access your project:
    ```
    gcloud auth login
    ```
`
Configure your project for gcloud, where [PROJECT-ID] is your Cloud Platform project ID:

   ```
    gcloud config set project [PROJECT_ID]
    ```
If you don't know your project ID, run the following command:

    ```
    gcloud projects list
    ```



    