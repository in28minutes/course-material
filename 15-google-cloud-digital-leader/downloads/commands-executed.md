## Commands Executed

Here are the commands executed during the course. 

Please refer back to them if you have any problems.

### Compute Engine
```
sudo su
apt update 
apt install apache2
ls /var/www/html
echo "Hello World!"
echo "Hello World!" > /var/www/html/index.html
echo $(hostname)
echo $(hostname -i)
echo "Hello World from $(hostname)"
echo "Hello World from $(hostname) $(hostname -i)"
echo "Hello world from $(hostname) $(hostname -i)" > /var/www/html/index.html
sudo service apache2 start


#!/bin/bash
apt update 
apt -y install apache2
echo "Hello world from $(hostname) $(hostname -I)" > /var/www/html/index.html


#!/bin/bash
echo "Hello world from $(hostname) $(hostname -I)" > /var/www/html/index.html
service apache2 start


```

### App Engine

```
cd default-service
gcloud app deploy
gcloud app services list
gcloud app versions list
gcloud app instances list
gcloud app deploy --version=v2
gcloud app versions list
gcloud app browse
gcloud app browse --version 20210215t072907
gcloud app deploy --version=v3 --no-promote
gcloud app browse --version v3

```

### Kubernetes

```
gcloud config set project my-kubernetes-project-304910
gcloud container clusters get-credentials my-cluster --zone us-central1-c --project my-kubernetes-project-304910
kubectl create deployment hello-world-rest-api --image=in28min/hello-world-rest-api:0.0.1.RELEASE
kubectl get deployment
kubectl expose deployment hello-world-rest-api --type=LoadBalancer --port=8080
kubectl get services
kubectl get services --watch
curl 35.184.204.214:8080/hello-world
kubectl scale deployment hello-world-rest-api --replicas=3
gcloud container clusters resize my-cluster --node-pool default-pool --num-nodes=2 --zone=us-central1-c
kubectl autoscale deployment hello-world-rest-api --max=4 --cpu-percent=70
kubectl get hpa
```

### Databases - Cloud SQL, Cloud Spanner and Cloud BigTable

```
# Cloud SQL
gcloud sql connect my-first-cloud-sql-instance --user=root --quiet
gcloud config set project glowing-furnace-304608
gcloud sql connect my-first-cloud-sql-instance --user=root --quiet
use todos
create table user (id integer, username varchar(30) );
describe user;
insert into user values (1, 'Ranga');
select * from user;

#Cloud SQL Auth Proxy
gcloud sql connect my-first-cloud-sql-instance --user=root --quiet
mysql -u root -p --host 35.193.189.63
wget https://dl.google.com/cloudsql/cloud_sql_proxy.linux.amd64 -O cloud_sql_proxy
chmod +x ./cloud_sql_proxy
mysql -u root -p --host 127.0.0.1
./cloud_sql_proxy -instances=glowing-furnace-304608:us-central1:my-first-cloud-sql-instance=tcp:3306

# Cloud Spanner
CREATE TABLE Users (
  UserId   INT64 NOT NULL,
  UserName  STRING(1024)
) PRIMARY KEY(UserId);

```