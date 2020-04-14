# infracore-fluentd
Custom fluentd image for our logging stack based on the [Kubernetes project fluentd container](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/fluentd-elasticsearch/fluentd-es-image)

## Significant changes from upstream

- Add `fluent-plugin-grafana-loki` to the Gems built for the container because the plugin requires native extensions and native extensions cannot be added at runtime due to all dev tools being unavailable (which is probably good security/reproducability practice).

## Build

```
# create TAG and latest version tagged images using Docker
make build
# push TAG and latest to PREFIX
make push
```
