# rhdg-demo

oc create project rhdg-demo

oc create sa cluster1-sa

oc adm policy add-cluster-role-to-user cluster-admin system:serviceaccount:rhdg-demo:cluster1-sa

oc sa get-token cluster1-sa > cluster1-sa.txt

oc create secret generic cluster1-sa-token --from-literal=token=$(cat cluster1-sa.txt)

