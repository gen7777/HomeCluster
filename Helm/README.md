# infra_k8s

INSTALL из текущего каталога !
_______________________________

1. 
~~~~~~~~~~~~~~~~

Victoriametrics:
helm -n victoria    install victoria-agent-hq      -f ./vmagent-victoria.yaml      ./helm-charts/victoriaMetrics/victoria-metrics-agent
helm -n victoria    install victoria-cluster       -f ./vmcluster-victoria.yaml    ./helm-charts/victoriaMetrics/victoria-metrics-cluster
helm -n victoria    install alertmanager-hq        -f ./alertmanager-victoria.yaml ./helm-charts/victoriaMetrics/alertmanager
helm -n victoria    install nodeexporter-hq        -f ./nodeexporter-victoria.yaml ./helm-charts/victoriaMetrics/node-exporter
helm -n victoria    install victoria-alert-hq      -f ./alert-victoria.yaml        ./helm-charts/victoriaMetrics/victoria-metrics-alert
helm -n victoria    install victoria-alert-hq      -f ./alert-victoria.yaml        ./helm-charts/victoriaMetrics/victoria-metrics-alert
helm -n victoria    install grafana-monitoring      -f ./grafana-monitoring.yaml        ./helm-charts/grafana

kube-state-metrics устанавливается просто через apply в оба кластера:
k  apply -f /helm-charts/victoriaMetrics/kube-state-metrics
