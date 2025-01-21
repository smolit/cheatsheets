# Docker Cheat Sheet

### Import container image from .tgz
        docker load -i downloads/solace-pubsub-enterprise-10.8.1.176-docker.tar.gz

### File size of your containers,
        docker ps --size
 
### show docker disk usage
  
        docker system df
  
  more detailed information on space usage:
        
        docker system df --verbose
