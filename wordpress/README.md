# Deploying WordPress and MySQL with Persistent Volumes
https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/

kustomization.yaml contains:
- a Secret generator
- MySQL resource configs
- WordPress resource configs

## Apply the directory by
```bash
kubectl apply -k ./
```
## Verify
1. The Secret exists
```bash
  kubectl get secrets
```
2. PersistentVolume got dynamically provisioned:
```bash
  kubectl get pvc
```
3. The Pod is running by running the following command:
```bash
  kubectl get pods
```
4. The Service is running:
```bash
  kubectl get services wordpress
```
5. Get the IP Address for the WordPress Service:
```bash
minikube service wordpress --url
```
6. Copy the IP address, and load the page in your browser to view your site.

## Cleaning up
```bash
  kubectl delete -k ./
```