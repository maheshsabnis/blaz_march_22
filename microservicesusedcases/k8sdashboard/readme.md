https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/

kubectl proxy

https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md


kubectl -n kubernetes-dashboard get secret $(kubectl -n kubernetes-dashboard get sa/admin-user -o jsonpath="{.secrets[0].name}") -o go-template="{{.data.token | base64decode}}"