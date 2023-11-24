# infra_k8s

INSTALL из текущего каталога !
_______________________________

1. 
~~~~~~~~~~~~~~~~

Victoriametrics:
helm -n victoria    upgrade victoria-agent-hq      -f ./values-hq/vmagent-victoria.yaml      ./helm-charts/victoriaMetrics/victoria-metrics-agent
helm -n victoria    install victoria-cluster       -f ./vmcluster-victoria.yaml    ./helm-charts/victoriaMetrics/victoria-metrics-cluster
helm -n victoria    upgrade alertmanager-hq        -f ./values-hq/alertmanager-victoria.yaml ./helm-charts/victoriaMetrics/alertmanager
helm -n victoria    upgrade nodeexporter-hq        -f ./values-hq/nodeexporter-victoria.yaml ./helm-charts/victoriaMetrics/node-exporter
helm -n victoria    upgrade victoria-alert-hq      -f ./values-hq/alert-victoria.yaml        ./helm-charts/victoriaMetrics/victoria-metrics-alert


kube-state-metrics устанавливается просто через apply в оба кластера:
k  apply -f /helm-charts/victoriaMetrics/kube-state-metrics
