# K8sPersitentVolCluster
Create a k8S multi node cluster with Persistent static volume and deploy a Web Application over Apache Web Server

STEPS TO CREATE:
1. Just start minikube service on your local machine.
2. Login inside your worker node and create a folder called `filename` in root `/` directory with command : `mkdir /filename`
3. Use command `kubectl create -f CompleteStruct.yml` to create a persistentVolume on your worker node, a persistent volume claim for your cluster and a single replica deployment with single container having image of Apache WebServer along with a load balancer with NodePort that will expose your app outside on 30400 port.
4. Create a simple php file in your pod directory `/var/www/html` by entering inside it with command: `kubectl exec -it [pod-name] bash`. you can get the pod name by typing `kubectl get pods`.
5. Now, everything is done. Type `minikube service list` and then grab the ip with port 30400 and see on the web browser.
6. Congratulations! Setup is done. Even if your pod is closed or deleted accidently. after few seconds your server will be up again with the same data.
