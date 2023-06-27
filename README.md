


Use namespace name "local"  namespace:local
  
sed -i 's/  namespace: vote/  namespace: local/g' * //replace namespace name from "vote" to "local"

helm install my-release oci://registry-1.docker.io/bitnamicharts/argo-cd

kubectl get ingress -n local

kubectl patch svc argocd-server  -p '{"spec": {"type": "LoadBalancer"}}'

kubectl get svc  ---> verify service name of argocd-server
 argo password - echo "Password: $(kubectl -n default get secret argocd-secret -o jsonpath="{.data.clearPassword}" | base64 -d)"--  IT4tL8ZyuJ
 argo username - admin




 ![image](https://github.com/Sush032/kube/assets/86153084/6df9ccee-303d-48b8-a4b9-b016c5a59c4c)



 ![image](https://github.com/Sush032/kube/assets/86153084/5867ac2c-6207-4d0d-977f-d1731858766e)



 ![image](https://github.com/Sush032/kube/assets/86153084/ceceb34d-bdf3-4ace-9517-e4e779ff63e7)

 Argocd dashboard:-


 
![image](https://github.com/Sush032/kube/assets/86153084/a50f2d54-2b97-42c8-a279-fbf71ef49feb)


![image](https://github.com/Sush032/kube/assets/86153084/0d172145-4160-4a84-936e-9b75bbdcdae7)


![image](https://github.com/Sush032/kube/assets/86153084/6d83f72d-d024-4cf4-8835-ce92f7e14c72)



![image](https://github.com/Sush032/kube/assets/86153084/84722620-365d-4b5b-9ff1-7ffb231472a9)


![image](https://github.com/Sush032/kube/assets/86153084/2d139d29-18bf-4123-a218-5dfd4b4aa304)




kubectl get all -n local : it will display the pods,deployment and replicaset








