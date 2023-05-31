kubectl proxy

http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

kubectl -n kubernetes-dashboard create token admin-user

helm -n lksg-tool template lksg-tool -s templates\ingress.yaml .
helm -n lksg-tool install lksg-tool --set auth.postgresPassword=docker --set auth.database=lksg-tool .
helm -n lksg-tool install lksg-tool --set postgresql.auth.password=lksg_tool --set postgresql.auth.username=lksg_tool --set postgresql.auth.database=lksg_tool .

kubectl delete -n lksg-tool persistentvolumeclaim data-lksg-tool-postgresql-0

lksg-tool-postgresql.lksg-tool.svc.cluster.local


helm -n lksg-tool uninstall lksg-tool
kubectl delete -n lksg-tool persistentvolumeclaim data-lksg-tool-postgresql-0
helm -n lksg-tool install lksg-tool --set postgresql.auth.password=lksg_tool --set postgresql.auth.username=lksg_tool --set postgresql.auth.database=lksg_tool .