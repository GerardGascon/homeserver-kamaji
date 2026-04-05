# TrueNAS Docker Deployment

**Important:** Before setup, please configure the networks

## Networks

### Nginx Proxy Manager

Network used mainly to publicly expose services through Nginx.

```bash
docker network create -d bridge nginx-proxy-manager
```

### Analytics

Network used to communicate analytics services (Grafana, Prometheus, etc.) between them.

```bash
docker network create -d bridge analytics
```
