```sh
firewall-cmd --add-port={7946/tcp,7946/udp} --permanent
firewall-cmd --reload

kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.10.2/manifests/namespace.yaml
kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.10.2/manifests/metallb.yaml

kubectl apply -f namespace.yaml
kubectl apply -f metallb.yaml

kubectl apupy -f config.yaml
```
