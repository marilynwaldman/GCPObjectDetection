# Use a Docker File on Google Cloud Platform Container Image
 
## Build the Dockerfile and upload it to GCP.  Instruction found [here](https://cloud.google.com/container-builder/docs/quickstarts/dockerfile)

Change directory: 

     cd DockerImage
     ls -l
     
You should see Dockerfile - it will built an uploaded to GCP.
  

### Log in to Google Cloud

Authorize gcloud to access your project:
    
    gcloud auth login
    
Configure your project for gcloud, where [PROJECT-ID] is your Cloud Platform project ID:
  
    gcloud config set project [PROJECT_ID]
   
If you don't know your project ID, run the following command:
  
    gcloud projects list
  

### Build and push your Dockerfile to GCP


To submit a build request using your Dockerfile, run the following command from the directory containing your application code, Dockerfile, and any other assets:


    gcloud container builds submit --tag gcr.io/[PROJECT-ID]/[IMAGE] .

where

[PROJECT-ID] is your Cloud Platform project ID
[IMAGE] is object-detect or whatever you want to name your docker image.

Check that your image is built on GCP. Run the following command:

    gcloud container images list


### Make the docker image available to container instances.  

Per instructions [here](https://cloud.google.com/container-registry/docs/access-control)

Display your project's Cloud Storage buckets:

    gsutil ls

Mark all current objects, including the image you just pushed, in your registry public by running the following command in your shell or terminal window:

    gsutil acl ch -r -u AllUsers:READ gs://artifacts.[PROJECT-ID].appspot.com

Make your registry's bucket publicly accessible:

    gsutil acl ch -u AllUsers:READ gs://artifacts.[PROJECT-ID].app



     






    