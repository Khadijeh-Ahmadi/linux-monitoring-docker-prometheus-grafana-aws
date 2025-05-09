
Ce projet m’a permis de comprendre les bases de la supervision. En plus,j’ai appris à mettre en place un système de monitoring simple en utilisant Docker, Prometheus et Grafana.
J’ai tout fait sur une machine EC2 d’AWS. J’ai pu tester moi-même comment ces outils s’intègrent pour surveiller un serveur.

Composants utilisés :

- Prometheus pour collecter les métriques
- Node Exporter pour exposer les données système du serveur
- Grafana pour créer des dashboards visuels

## Lancement des services :

1. Démarrer Node Exporter :

```bash
docker run -d --name node_exporter -p 9100:9100 prom/node-exporter

Démarrer Prometheus:

2. docker run -d \
  --name prometheus \
  -p 9090:9090 \
  -v $(pwd)/prometheus.yml:/etc/prometheus/prometheus.yml \
  prom/prometheus

3. Démarrer Grafana:

docker run -d --name=grafana -p 3000:3000 grafana/grafana

