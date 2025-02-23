Create a Secret on argocd namespace : 


kubectl create secret docker-registry ecr-secret \
  --docker-server=365657944743.dkr.ecr.us-east-1.amazonaws.com \
  --docker-username=AWS \
  --docker-password=$(aws ecr get-login-password --region us-east-1) \
  --namespace argocd
