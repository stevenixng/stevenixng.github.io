---
title: AKS
---

####  log into azure
    az login

#### get account list and set
    az account list -o table
    az account set --subscription '<sub-name>'

#### get aks credentials so you can use kubectl
    az aks list -o table
    az aks get-credentials --resource-group <resource_grp> --name <name>

#### kubectl
    kubectl get namespace
    kubectl get nodes
    kubectl get services
    kubectl get pods --all-namespaces
    kubectl get sc

#### storage
    kubectl get pvc -n <pvcname>
    kubectl get pv -n <pvname>
    kubectl describe pvc <claimname> -n <namespace>

#### troubleshooting
    kubectl describe pods -n <namespace>
    kubectl logs <logname> -n <namespace>
    kubectl logs <podname> -n <namespace>
    kubectl exec --stdin --tty opensearch-cluster-master-0 -n <namespace> -- /bin/bash
    curl --insecure -u admin:admin 'https://<cluster>:9200/_cat/indices?v'

#### restart
    kubectl rollout restart deployment <deployment> -n <namespace>
    kubectl delete pod <pod> -n <namespace>
