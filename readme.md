created 2 pods in diff diff namespaces and created a service for pod-a and then start shell session(kubectl exec -it pod-b --namespace=namespace2 -- /bin/bash) for pod-b using commands
using a command like curl http://service-a.namespace1.svc.cluster.local check if service is accessible from pod-b in namespace2



other way: through ip
kubectl get pod pod-a -n namespace1 -o wide (in this u can get a pod ip)
now again start shell session from pod-b (kubectl exec -it pod-b -n namespace2 -- /bin/bash)
now use curl command from pod-b to access pod-a (curl http://10.244.0.2)


