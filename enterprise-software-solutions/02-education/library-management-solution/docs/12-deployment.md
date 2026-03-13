# 12 - Library Deployment Strategy

## Reliability & Uptime
- **Hybrid Mirroring**: Maintaining a local cache of catalog metadata inside the school to ensure circulation desk can operate during internet outages.
- **Containerization**: Deploying Librarian and Student portals as independent microservices for granular scaling.

## Data Migration
- **ETL Pipelines**: Automated scripts for importing legacy XLS/CSV catalog data into the new MARC-compliant schema.

## Monitoring
- **Hardware Health**: Real-time monitoring of RFID gates and scanner connectivity status via Prometheus/Grafana.
