# kibana-helm-chart
This is a kibana helm chart that will be part of the ELK stack.
# Getting Started
1. Create `monitoring` namespace, by running the following command:
```shell
kubectl create ns monitoring
```
2. Pull `kibana` dependencies, by running the following command:
```shell
helm dependency update ./kibana-helm-chart
```
3. Create a secret that will hold elasticsearch credentials. It should look like this:
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: kibana-elastic-secret
  namespace: monitoring
data:
  username: ZWxhc3RpYw==
  password: RWxhc3RpYzJQYXNzd29yZA==
```
4. Install the chart, by running this command:
```shell
helm install kibana kibana-helm-chart -f kibana-helm-chart/values.yaml -n monitoring
```
