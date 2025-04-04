# Docker Commands :

### To create a Dockerfile

```
docker init
```

### To build docker image

```
docker build -t <image-name>:<tag> .
```

### To run dockerfile

#### Use `-d` flag to run container in detach mode

```
docker run -it -p 8000:8000 --name <container-name> <image-name>
```

### To open shell inside container (get inside container)

```
docker exec -it <container-name> bash
```

# Kubernetes Commands :

### To create kubernetes deployment

```
kubectl create deployment flask-app-deployment \
--image=nginx \
--replicas=3 \
--dry-run=client -o yaml > deployment.yml
```

### To create kubernetes service

```
kubectl expose deployment flask-app-deployment \
--name=flask-app-service \
--port=80 \
--target-port=8300 \
--type=LoadBalancer \
--dry-run=client -o yaml > service.yml
```

### To load the locally running Image into minikube

```
minikube image load backend-image
```

### To restart the deployment

```
kubectl rollout restart deployment flask-app-deployment
```

### To assign IP to LoadBalancer or ClusterIP

```
minikube service flask-app-service --url
```

### To port-forward for LoadBalancer or ClusterIP

```
kubectl port-forward service/flask-app-service 8080:80
```

# Ansible Commands :

### Default file location: `inventory.yml/inventory.ini`

```
/etc/ansible/hosts                               # Edit default inventory file
```

### To run ansible `playbooks`

```
ansible-playbook -i inventory playbook-name.yml
```

#### if you do not want to mention `-i inventory` in above command, you can use below command

```
ansible-playbook playbook-name.yml               # This command will refer Default inventory file
```

### To encrypt & decrypt `.yml/.yaml` file

```
ansible-vault encrypt secret.yml
ansible-vault decrypt secret.yml
```
