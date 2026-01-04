# Daemonset

## what is Daemonset?
- Object to run specific pod on each node
- when u delete this pod manually , daemonset will immediately recreate it again (Daemonset create Replicaset by default)
- if any new node join the cluster, daemon will create this pod automatically
- if u delete daemonset , all daemonset pods will deleted

## when can use it?
- monitring
- logging
- collect logs
- network plugin
- storage plugin
## examples of Daemonsets
- kubeproxy as network plugin 
- CNI
- CSI
## Will a DaemonSet run on the control plane node?
if u have managed cluster as EKS , u cant run it 
if u have self-managed cluster ,u can do this but must add toleration allowing it to tolerate that taint(node-role.kubernetes.io/control-plane:NoSchedule).

## Basic Commands
- Create a Daemonset: `kubectl apply -f <ds.yaml>`  
- List all Daemonset: `kubectl get ds`
- List Daemonset with details: `kubectl get ds -o wide`
- Describe a Daemonset: `kubectl describe ds <Daemonset-name>`
- Delete a Daemonset: `kubectl delete ds <Daemonset-name>`  
