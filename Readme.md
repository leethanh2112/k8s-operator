# Requirement:
```
- Install Ansible 2.9
- Define input values for ansible_roles ( k8s-operator )
- Running this script on master node 
```

## Install Ansible
```
- Reference: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
```

## Define input values:
Open input.yml file
```
deployment:
  - app_name:  xyz               ( define the application name in k8s )
    namespace: namespace-1       ( set namespace for application in k8s )
    image_registry: nginx:latest ( put in your image that you need to deploy into k8s )
    replicas: 5                  ( limit number pods )
    port: 80                     ( container port number )
    protocol: TCP                ( TCP or UDP )
```

## Run Ansible Task:
```
ansible-playbook k8s-operator.yml 
```

## Verify pods in K8s
```
kubectl get pod -n namespace-1
kubectl get pod -n namespace-2
```
    
        
