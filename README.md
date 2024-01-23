# Build a chart example

Use this small chart to create your own nginx web server!

ref: https://opensource.com/article/20/5/helm-charts

# Build template

helm template buildachart --values ./buildachart/values.yaml --skip-tests

# Build manifests

helm template buildachart --values ./buildachart/values.yaml --skip-tests > ./buildachart/manifests.yaml

# Chart install (verify on openlens)

helm install releaseversion buildachart --values ./buildachart/values.yaml

# Chart uninstall

helm uninstall releaseversion

# Apply manifests

kubectl apply -f ./buildachart/manifests.yaml

# Verify Apply

kubectl get pods,svc,deployments

# Forward port (enter http://localhost)
kubectl port-forward pod/cherry-chart-6ffb89668d-mwksb 80:80
