# grafana_container  
 

 
git clone https://github.com/mshow34jt/grafana_container  
cp -a grafana_container/grafana {storage dir}  
### to run in docker directly  
docker run –rm -d --network host –name Grafana  -v/etc/localtime:/etc/localtime -v {storage dir}/grafana:/var/lib/grafana -v {storage dir}/grafana/etc/grafana:/etc/grafana  grafana/grafana   

### to use singularity  
singularity build grafana.sif docker://grafana/grafana  
midir {storage dir}/images    
cp grafana.sif <storage dir>/images   
singularity instance start --bind /etc/localtime:/etc/localtime --bind {storage dir}/grafana:/var/lib/grafana --bind {storage dir}/grafana/etc/grafana:/etc/grafana {storage dir}/images/grafana_latest.sif Grafana    

After Instance is started, run singularity run instance://Grafana bash to start the server  
