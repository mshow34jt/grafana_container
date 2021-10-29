# grafana_container
singularity build grafana.sif docker://grafana/grafana

git clone https://github.com/mshow34jt/grafana_container
cp -a grafana_container/grafana /storage/nvme0n1/ncsa
singularity instance start --bind /etc/localtime:/etc/localtime --bind /storage/nvme0n1/ncsa/grafana:/var/lib/grafana --bind /storage/nvme0n1/ncsa/grafana/etc/grafana:/etc/grafana /storage/nvme0n1/ncsa/images/grafana_latest.sif Grafana
