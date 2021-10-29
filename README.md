# grafana_container
docker pull grafana:latest
singularity build grafana_latest.sif docker-daemon://grafana:latest

singularity instance start --bind /etc/localtime:/etc/localtime --bind /storage/nvme0n1/ncsa/grafana:/var/lib/grafana --bind /storage/nvme0n1/ncsa/grafana/etc/grafana:/etc/grafana /storage/nvme0n1/ncsa/images/grafana_latest.sif Grafana
