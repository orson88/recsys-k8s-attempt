# recsys-k8s-attempt
## A repo for my first attempt at learning k8s and mlops practises via a recsys task


### The two aims of this project
1. Learn basics of K8s
2. Create a full ml-based service and take a glimpse at why exactly are ML Operations are needed and try to create some)

## Replication
### Requirements
1. Kubernetes, minikube
2. Linux
3. Docker
4. Helm
   
Clone the repo
Start cluster-init.sh
go into postgre pod and create train and test tables from .csv files loaded into them

## Overview of the service
### Stack
| Element | Implementation | How it could be improved |
| ------- | -------------- | --------------- |
| Infrastructure | minikube | Add an ingress contoller so the networking would be more secure and centalized |
| Backend | Python FastAPI | Make proper async architecture and add warnings and errors |
| Frontend | Streamlit | Change the tool)) Streamlit is easy to learn - nowhere to be mastered. It has a bad habit of reloading the whole page after each action of the user, which makes it a bad frontend solution. |
| Storage | PostgreSQL | Add proper ETL procedures for data manipulations (AirFlow or Cron) |
| RecSys model | Implicit.ALS + Optuna | There are many ways to improve, but it was not the aim. First of all change the data set, cause its pretty limiting in terms of feature engineering and im not that good in DL and MF for pure user-item recsys |  
| Monitoring | Grafana + Prometheus | No alerting, only dashboards. Dashboard itself is not perfect. Gotta take some time to learn about Grafana's syntax |
| Versioning | Github | Idk what to write here, but a total IaC would be better)))) |
| Virtualization | K8s + docker | Initializing a local docker registry would be good, also pulling the cluster state from github would also be a better practice (for IaC) |
| MLOps | Manual python script + W&B | Should add a proper orchestrated procedure for new models and add serving, so that for inference the fastapi backend would pull models from W&B rather than using the local model object file after manual script run. |

#### Architecture overview
<img src="https://github.com/orson88/recsys-k8s-attempt/assets/62896830/64a9c291-0655-4321-8a51-8f3ea6326f97)https://github.com/orson88/recsys-k8s-attempt/assets/62896830/64a9c291-0655-4321-8a51-8f3ea6326f97" width="800" height="675">

### What the service does
1) Find yourself in the users list
![image](https://github.com/orson88/recsys-k8s-attempt/assets/62896830/cf3cf82c-4440-4712-a1f7-26fdbe5291dd)

2) Get 5 songs recomended
![image](https://github.com/orson88/recsys-k8s-attempt/assets/62896830/afa5332f-81a5-4133-ad02-162fe0b15e4e)

3) Register or add new reactions
![image](https://github.com/orson88/recsys-k8s-attempt/assets/62896830/fa6c5231-aa39-4baa-8d59-68d936a0b72f)


### Results of research and practise: What is better to do and what i will learn next
1. DevOps
   1. Strives for the IaC architecture, add the K8S operator, which would request a cluster from the git during initialization.
   2. Add CI / CD and testing: on a new commit, build the back and front, check the performance.
   3. Add smart replication rules for data nodes and rules to limit and stop other pods when retraining starts.
2. MLOps
   1. Add the AirFlow orchestrator to easily and conveniently run additional training with DAGs.
   2. Change wandb to minio (local S3 replacement) and mlflow (for logging models and metrics)
   3. Change the approach to choosing a new model. At the moment, such things as data drift, concept drift, etc. are not taken into account.
   4. Add automatic serving
3. Data Engineering and Load
   1. Use AirFlow to set up ETL/ELT scripts to manage data expansion (for example, when new users appear).
   2. Insert a queue layer. To distribute the load on the service and the database, deploy Kafka.
