# elk-xpack-k8s

setup first before doing ssl enable

then set password

kubectl exec -it $(kubectl get pods | grep elasticsearch-client | sed -n 1p | awk '{print $1}') -- bin/elasticsearch-setup-passwords auto -b

after that enable ssl 

store password in kubernetes
-----
kubectl create secret generic elasticsearch-pw-elastic --from-literal password=Xp6krQZbQyYNmBFy7UaN --namespace=kube-system

encode certificate by below command
------
base64 --w 0 ca.crt

