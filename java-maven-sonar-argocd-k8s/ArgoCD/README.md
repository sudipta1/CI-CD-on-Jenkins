We will Install ArgoCD by using Helm : 

1. helm repo add argo https://argoproj.github.io/argo-helm
2. helm repo update
3. helm install argocd argo/argo-cd --namespace argocd --create-namespace
4. Get the Secret Password and covert it to {echo <initialadminpassword> | base64 -d}
5. kubectl port-forward svc/argocd-server -n argocd 8000:443

Create a Secret file on argocd namespace : 

kubectl create secret docker-registry ecr-secret \back_slash
  --docker-server=365657944743.dkr.ecr.us-east-1.amazonaws.com \back_slash
  --docker-username=AWS \back_slash
  --docker-password=$(aws ecr get-login-password --region us-east-1) \back_slash
  --namespace argocd
