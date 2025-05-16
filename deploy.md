### Kubernetes, Deployment

#### Kubernetes, minikube  
Install kubernetes (k8s) and minikube  
   1. Create minikube 2 nodes cluster and upload :  
      `$> sh auxillary/minikube/mn-cluster-creation.sh`  
   2. 

> [!Tip]
> 
> It might be useful to upgrade kubectl and minikube to latest versions  
> https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-kubectl-binary-with-curl-on-linux  
> 
> downgrade docker to 24 version:  
> https://docs.docker.com/engine/install/ubuntu/#install-using-the-convenience-script  
> 
> helm installation:
> https://helm.sh/docs/intro/install/#from-apt-debianubuntu

> [!Tip]
>
> Kubernetes commands
>
> K8s cluster info  
> `$> kubectl cluster-info` 
>
> K8s get pods,deployments,services  
> `$> kubectl -n <namespace> get pods,deployments,services`
> 
> K8s get all  
> `$> kubectl -n <namespace> get all`
> 
> Redirect port  
> `$> kubectl --namespace <namespace> port-forward $POD_NAME 8080:$CONTAINER_PORT`  
>  

> [!Tip]
> 
> Minikube commands
> 
> minikube dashboard  
> `$> minikube -p mn dashboard --url`  
> (`alias min="minikube -p mn"`)

> [!Tip]
> 
> Helm commands
> 
> Add repos  
> `$> helm repo add bitnami https://charts.bitnami.com/bitnami`  
> `$> helm repo add brigade https://brigadecore.github.io/charts`
> 
> List locally installed charts  
> `$> helm search repo bitnami`
> 
> Search "kash" chart in local repos  
> `$> helm search repo kash`
> 
> Update to latest list of charts  
> `$> helm repo update`
> 
> Install chart (instantiate release)  
> `$> helm install bitnami/mysql --generate-name`
> 
> Releases list  
> `$> helm list`
> 
> Unistall release  
> `$> helm uninstall mysql-<...>`
> 
> Unistall release with history  
> `$> helm uninstall mysql-<...> --keep-history`
>
> Releases list (--uninstalled, --all)  
> `$> helm list --uninstalled`  
> `$> helm list --all`  
> 
> Help  
> `$> helm get -h`
> 
> Artifact Hub list  
> `$> helm search hub`
> 
> Search WordPress in Artifact Hub  
> `$> helm search hub wordpress`  
> 
> Install chart with specified name    
> `$> helm install happy-panda bitnami/wordpress`
> 
> Release status of "happy-panda"    
> `$> helm status happy-panda`
> 
> Configurable options for chart (-f, --values - file, --set - command line)     
> `$> helm show values bitnami/wordpress`  
> `$> echo '{mariadb.auth.database: user0db, mariadb.auth.username: user0}' > values.yaml`  
> `$> helm install -f values.yaml bitnami/wordpress --generate-name`  
> `$> helm install --set name=value --set outer.inner=value name0 bitnami/wordpress`  
> https://helm.sh/docs/intro/using_helm/#customizing-the-chart-before-installing
> 
> Upgrade release    
> `$> helm upgrade -f panda.yaml happy-panda bitnami/wordpress`  
>
> Rollback release to revision: 2     
> `$> helm rollback happy-panda 2`
>
> History for release     
> `$> helm history happy-panda`  
>
> Remove repository of "bitnami"     
> `$> helm repo remove bitnami`  
> 
> See also:  
> https://helm.sh/docs/intro/quickstart/  
> https://helm.sh/docs/intro/using_helm/

> [!Tip]
> 
> Development chart
> 
> Create helm chart: "helmtest"  
> `$> helm create helmtest`  
>
> Lint helm chart  
> `$> helm lint helmtest`  
>
> Package helm chart  
> `$> helm package helmtest`
>
> Install helm chart  
> `$> helm install helmtest ./helmtest-0.1.0.tgz`
>
> Load chart to repository  
> https://helm.sh/docs/topics/chart_repository/  
> https://medium.com/@gerkElznik/provision-a-free-personal-helm-chart-repo-using-github-583b668d9ba4
> 
