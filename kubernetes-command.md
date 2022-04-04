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

> kubectl api-resources
> kubectl apply -f apps.yaml --namespace=argocd
> kubectl delete all --all -n argocd
> echo -n 'admin' | base64
> kubectl apply -f configmap.yaml --namespace=goapp-namespace
> kubectl apply -f goapp-secret.yaml --namespace=goapp-namespace
> docker build -t goapp-database .
> kubectl apply -f goapp-database.yaml --namespace=goapp-namespace
> kubectl get secret
> kubectl get pod
> kubectl describe pod goapp-database-deployment-5bd65579cf-w9f2v
> kubectl get services
> kubectl get pod -o wide
> kubectl get pod --namespace=goapp-namespace
> kubectl get all | grep mongodb
> docker build -t goapp .
> kubectl apply -f goapp.yaml --namespace=goapp-namespace
> kubectl describe pod goapp-deployment-6c658776dc-jlrmj
> minikube service --url goapp-service
> minikube service --url goapp-database
> kubectl logs -f pod/goapp-deployment-6c658776dc-9sfcr
> kubectl exec -it pod/goapp-database-deployment-756dc74c4c-xz4sx -- psql -d goapp -U admin
> select * from workers;


docker rmi $(docker images --filter "dangling=true" -q --no-trunc)
docker build -t goapp .
docker runrm -it -p 8080:8080 goapp
http://localhost:8080
http://localhost:8080/worker?id=123
docker build -t goapp-database .
docker run --rm -it -p 5000:5432 goapp-database
psql -d goapp -U postgres