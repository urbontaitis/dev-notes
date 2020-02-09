# Docker cli commands

```bash
#Stop all 
docker stop $(docker ps -a -q)

#Remove all 
docker rm $(docker ps -a -q)
```