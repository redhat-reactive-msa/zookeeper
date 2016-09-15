# Zookeeper

The Vert.x cluster is going to be maintained by a Zookeeper server. So we need to deploy a pod with Zookeeper: 

----
oc new-build --binary --name=zookeeper -l app=zookeeper
oc start-build zookeeper --from-dir=. --follow
oc new-app zookeeper -l app=zookeeper
oc expose service zookeeper
----