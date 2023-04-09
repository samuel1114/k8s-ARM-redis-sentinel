# k8s-ARM-redis-sentinel

$kubectl delete --context arn:aws:eks:ap-south-1:xxxxxxxxxxxx:cluster/xxxxx-production --namespace infra -f redis/redis-sentinel-controller.yaml<br>
$kubectl delete --context arn:aws:eks:ap-south-1:xxxxxxxxxxxx:cluster/xxxxx-production --namespace infra -f redis/redis-controller.yaml<br>
$kubectl delete --context arn:aws:eks:ap-south-1:xxxxxxxxxxxx:cluster/xxxxx-production --namespace infra -f redis/redis-master.yaml<br>

$kubectl apply --context arn:aws:eks:ap-south-1:xxxxxxxxxxxx:cluster/xxxxx-production --namespace infra -f redis/redis-master.yaml<br>
$kubectl apply --context arn:aws:eks:ap-south-1:xxxxxxxxxxxx:cluster/xxxxx-production --namespace infra -f redis/redis-sentinel-service.yaml<br>
$kubectl apply --context arn:aws:eks:ap-south-1:xxxxxxxxxxxx:cluster/xxxxx-production --namespace infra -f redis/redis-controller.yaml<br>
$kubectl apply --context arn:aws:eks:ap-south-1:xxxxxxxxxxxx:cluster/xxxxx-production --namespace infra -f redis/redis-sentinel-controller.yaml<br>

kubectl scale rc redis --replicas=3 --context arn:aws:eks:ap-south-1:8xxxxxxxxxxxx:cluster/xxxxx-production --namespace infrastructure<br>
kubectl scale rc redis-sentinel --replicas=3 --context arn:aws:eks:ap-south-1:xxxxxxxxxxxx:cluster/xxxxx-production --namespace infrastructure<br>
