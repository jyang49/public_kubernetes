----------------------------------------------
Configure GKE to enalbe netwokr policy
----------------------------------------------

To enable network policy in an existing cluster, 

gcloud container clusters update standard-cluster-2 --update-addons=NetworkPolicy=ENABLED --zone asia-east1-a

gcloud container clusters update standard-cluster-2 --enable-network-policy --zone asia-east1-a

----------------------------------------------
Testing
----------------------------------------------

## create pods and networkpolicy

cd yaml
kubectl create -f .

## find pod IP

kubectl get po -o wide

## exec to admin pod

kubectl exec -it myapp-pod-admin /bin/sh

ping IP of pod "myapp-pod-prod"

Expected outcome: can ping

## exec to non-admin pod

kubectl exec -it myapp-pod-non-admin /bin/sh

ping IP of pod "myapp-pod-prod"

Expected outcome: cannot ping

 

