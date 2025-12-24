# PetShop Deployment

This repo contains:
- `docker-compose.yaml` for local development
- k8s/ manifests for Kubernetes / GKE (including MySQL + Zipkin + ConfigMaps)
- Optional CI/CD entrypoint (Jenkinsfile_gcp)

## Kubernetes (GKE)
- `k8s/config-maps.yaml` defines internal service URLs (Eureka, ConfigServer, MySQL, Zipkin).
- `k8s/mysql-deployment.yaml` deploys MySQL.
- `k8s/zipkin-deployment.yaml` deploys Zipkin.
- Each service repo contains its own `k8s/deployment.yaml` (and Service).

## Related
Full project overview:  
https://github.com/IslamHamada/petshop
