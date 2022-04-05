> minikube start
> minikube status
> eval $(minikube docker-env)
> kubectl get namespaces
> kubectl create namespace argocd
> kubectl delete namespace argocd
> kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
> kubectl get svc -n argocd
> kubectl port-forward -n argocd svc/argocd-server 8080:443
> login: 
    user: admin 
    password: kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
    > echo b2dZRjBDTE0yUG1XMUJMQ== | base64 --decode
> kubectl apply -f application.yaml
> export KUBE_EDITOR='code --wait'
> kubectl edit deployment -n myapp myapp-deploy