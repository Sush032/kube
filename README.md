


Use namespace name "local"  namespace:local
  
sed -i 's/  namespace: vote/  namespace: local/g' * //replace namespace name from "vote" to "local"

helm install my-release oci://registry-1.docker.io/bitnamicharts/argo-cd

kubectl get ingress -n local

kubectl patch svc argocd-server  -p '{"spec": {"type": "LoadBalancer"}}'

kubectl get svc  ---> verify service name of argocd-server
 argo password - kubectl -get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
 argo username - admin




 ![image](https://github.com/Sush032/kube/assets/86153084/6df9ccee-303d-48b8-a4b9-b016c5a59c4c)



 ![image](https://github.com/Sush032/kube/assets/86153084/5867ac2c-6207-4d0d-977f-d1731858766e)



 ![image](https://github.com/Sush032/kube/assets/86153084/ceceb34d-bdf3-4ace-9517-e4e779ff63e7)




 ![image](https://github.com/Sush032/kube/assets/86153084/14b73d44-c4c6-4b82-b473-ca506c2412ba)




