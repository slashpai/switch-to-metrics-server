# switch-to-metrics-server
Document pros and cons of switching to metrics server

## Testing

```
k scale deploy/cluster-monitoring-operator --replicas 0 -n openshift-monitoring
k delete apiservice v1beta1.metrics.k8s.io
```

```
k apply -f components.yaml
```

```
k delete deploy prometheus-adapter -n openshift-monitoring
```
