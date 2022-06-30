# Helm - Example - Install bitnami/mysql 

## Prerequisites 

  * kubectl needs to be installed and configured to access cluster
  * Good: helm works as unprivileged user as well - Good for our setup 
  * install helm on ubuntu (client) as root: snap install --classic helm 
    * this installs helm3
  * Please only use: helm3. No server-side comoponents needed (in cluster) 
    * Get away from examples using helm2 (hint: helm init) - uses tiller  

## Example 1 (runterladen):

```
helm repo add bitnami https://charts.bitnami.com/bitnami 
helm search repo bitnami
helm repo update 
helm pull bitnami/mysql
tar xzvf mysql-*.tar.gz 

```

## Example 1: We will setup mysql without persistent storage (not helpful in production ;o() 

```
helm repo add bitnami https://charts.bitnami.com/bitnami 
helm search repo bitnami 
helm repo update

helm install my-mysql bitnami/mysql


```


## Example 1 - continue - fehlerbehebung 

```
# Install with persistentStorage disabled - Setting a specific value 
helm install my-mysql --set primary.persistence.enabled=false bitnami/mysql
# Alternative if already installed 

# just as notice 
# helm uninstall my-mysql 

```

## Referenced

  * https://github.com/bitnami/charts/tree/master/bitnami/mysql/#installing-the-chart
  * https://helm.sh/docs/intro/quickstart/
