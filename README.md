# k8s-html
This repository has manifests to install simple nginx-based server, managed by k8s.

Also, this is for k8s custom controller.

See [here]() to get details of the custom controller.

## K8s environment
- kind: v0.20.0

## How to use?
1. Clone this Repository.

2. Make k8s cluster by using `kind`.
   ```shell
   kind create cluster --config kind-config.yaml
   ```

3. Register the cluster to `kubectl`.
   ```shell
   kubectl cluster-info --context kind-kind
   ```

4. Install ingress-controller by NGINX.
   ```shell
   kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
   ```

5. Apply k8s all resources.
   ```shell
   kubectl apply -f deployment.yaml -f service.yaml -f cm.yaml -f ingress.yaml
   ```

6. Get html resources from the cluster.
   ```shell
   curl http://localhost
   ```