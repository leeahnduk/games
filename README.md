# DosGames in Container
# git clone https://github.com/leeahnduk/games.git
# cd games
# tar –xvf mario.tar
# cd mario 
# docker build -t <region>-docker.pkg.dev/${PROJECT_ID}/mario:v1 . 
  docker images
  docker run -d --name mario -p 6080:80 <region>-docker.pkg.dev/${PROJECT_ID}/mario:v1 .
  docker ps
  gcloud auth configure-docker <region>-docker.pkg.dev
  docker push <region>-docker.pkg.dev/${PROJECT_ID}/mario:v1
  export PROJECT_ID=augmented-axe-354103
gcloud config set project $PROJECT_ID
gcloud config set compute/region <region>
  gcloud container clusters create-auto autopilot-cluster \
    --region <region> \
    --project=${PROJECT_ID} --cluster-version "1.20"
  kubectl apply -f mario.yml
watch kubectl get pods 
kubectl get service mario | awk 'NR == 2 {print $4}'

Get the URL and try to access the web server.
http://ip/vnc.html



  
