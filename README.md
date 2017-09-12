

1.  git clone git@github.com:marilynwaldman/GCPObjectDetection.git
2. gcloud compute instances create object-detection \
   --image-family gci-stable \
   --image-project google-containers \
   --zone us-central1-b --boot-disk-size=100GB \
   --machine-type n1-standard-4

3. gcloud compute firewall-rules create object-detection --allow tcp:8888,tcp:6006,tcp:5000

imperial-octane-178819


sudo docker run -p 6006:6006 -p 8888:8888 -p 5000:5000 gcr.io/tensorflow/tensorflow

open new terminal ssh
