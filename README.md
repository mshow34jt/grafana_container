# grafana_container
singularity build grafana.sif docker://grafana/grafana  
midir {storage dir}/images
  cp grafana.sif <storage dir>/images
git clone https://github.com/mshow34jt/grafana_container  
cp -a grafana_container/grafana {storage dir}  
singularity instance start --bind /etc/localtime:/etc/localtime --bind {storage dir}/grafana:/var/lib/grafana --bind {storage dir}/grafana/etc/grafana:/etc/grafana {storage dir}/images/grafana_latest.sif Grafana  


After Instance is started, run singularity run instance://Grafana bash to start the server  
