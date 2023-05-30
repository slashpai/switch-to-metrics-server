# switch-to-metrics-server
Document pros and cons of switching to metrics server

## Testing

```
k scale deploy/cluster-monitoring-operator --replicas 0 -n openshift-monitoring
```

```
k apply -f components.yaml
```

Check Pod Ready Status

```
k get pod -l k8s-app=metrics-server
```

Delete existing APIService pointing to prometheus-adapter and create APIService pointing to metrics-server

```
k delete apiservice v1beta1.metrics.k8s.io
k apply -f apiservice.yaml
```

or update respective fields in existing APIService to point to metrics-server


Delete prometheus-adapter deployment

```
k delete deploy prometheus-adapter -n openshift-monitoring
```
