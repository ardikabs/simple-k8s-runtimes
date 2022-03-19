# Overview

This repository is used for managing multiple Kubernetes runtimes supporting several ways deployment to the cluster such as:

* `kustomize`   : refer to the `clusters/<cluster_name>/kustomize` path
* `helmfile`    : refer to the `clusters/<cluster_name>/releases` path (require: `helm diff`)
* `kubectl`     : refer to the `clusters/<cluster_name>/manifests` path

about how to run the manager you can follow below command:

```bash
$ export PATH=$PATH:bin/
$ k8s-deployer diff <cluster_name>
$ k8s-deployer apply <cluster_name>
```

## Milestones

* [x] Create Kubernetes runtime management repository
* [ ] Building observability system architecture (monitoring part)
  * [x] Victoria Metrics as aggregator
  * [x] Prometheus as scraper on each cluster ([kube-prometheus](https://github.com/bitnami/charts/blob/master/bitnami/kube-prometheus), prometheus-community)
  * [ ] Prometheus-rules as alerting rule
  * [ ] Grafana as visualizer
  * [ ] Alertmanager as alert router
