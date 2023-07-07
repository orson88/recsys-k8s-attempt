# recsys-k8s-attempt
## A repo for my first attempt at learning k8s and mlops practises via a recsys task

### The two aims of this project
1. Learn basics of K8s
2. Create a full ml-based service and take a glimpse at why exactly are ML Operations are needed and try to create some)

### Overwiev of the service
| Element | Implementation | How it could be improved |
| ------- | -------------- | --------------- |
| Infrastructure | minikube | Add an ingress contoller so the networking would be more secure and centalized |
| Backend | Python FastAPI | Make proper async architecture and add warnings and errors |
| Frontend | Streamlit | Change the tool)) Streamlit is easy to learn - nowhere to be mastered. It has a bad habit of reloading the whole page after each action of the user, which makes it a bad frontend solution. |
| Storage | PostgreSQL | Add proper ETL procedures for data manipulations (AirFlow or Cron) |
| RecSys model | Implicit.ALS + Optuna | There are many ways to improve, but it was not the aim. First of all change the data set, cause its pretty limiting in terms of feature engineering and im not that good in DL and MF for pure user-item recsys |  

<img src="https://github.com/orson88/recsys-k8s-attempt/assets/62896830/64a9c291-0655-4321-8a51-8f3ea6326f97)https://github.com/orson88/recsys-k8s-attempt/assets/62896830/64a9c291-0655-4321-8a51-8f3ea6326f97" width="800" height="675">
