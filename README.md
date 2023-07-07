# recsys-k8s-attempt
## A repo for my first attempt at learning k8s and mlops practises via a recsys task

### The two aims of this project
1. Learn basics of K8s
2. Create a full ml-based service and take a glimpse at why exactly are ML Operations are needed and try to create some)

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
