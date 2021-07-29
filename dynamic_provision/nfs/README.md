# server
apt install -y nfs-server

# client
apt install -y nfs-client

# /etc/exportfs
/srv/nfs/kubedata   *(rw,sync,no_subtree_check,no_root_squash,no_all_squash,insecure)

# create resources
kubectl apply -f rbac.yaml
kubectl apply -f storage.yaml
kubectl apply -f deploy.yaml

# pvc spec
storageClassName: managed-nfs-storage
