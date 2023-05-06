# JFrog Metrics monitoring
## Install Prometheus and Grafana
### Install Prometheus
Prometheus：<https://prometheus.io/docs/prometheus/latest/installation/>
### Install Grafana
Grafana: <https://grafana.com/docs/grafana/latest/setup-grafana/installation/>
## Enable JFrog metrics
JFrog: <https://jfrog.com/help/r/jfrog-platform-administration-documentation/open-metrics>
## Configure Prometheus to collect metrics data
Configure in prometheus.yml
```html
  - job_name: "artifactory_metric"
    metrics_path: "/artifactory/api/v1/metrics"
    scheme: "https"
    basic_auth:
      username: "xxx"
      password: "xxx"
    static_configs:
      - targets: ["demo.jfrogchina.com"]

  - job_name: "xray_metric"
    metrics_path: "/xray/api/v1/metrics"
    scheme: "https"
    basic_auth:
      username: "xxx"
      password: "xxx"
    static_configs:
      - targets: ["demo.jfrogchina.com"]

```
## Configure Grafana
Import <https://github.com/JFrogChina/JFrog-monitoring/blob/main/Grafana/JFrog-metrics> in Granfana
# JFrog Stats monitoring
Artifactory Exporter: <https://github.com/peimanja/artifactory_exporter>
