dockers安装emby开心版
`ls /dev/dri

docker pull lovechen/embyserver

amilys/embyserver

docker run --name emby -d --net host --env UID=0 --env GID=0 --env GIDLIST=0 --device=/dev/dri:/dev/dri lovechen/embyserver:latest
`
docker安装moviepilot
`docker run -itd \
     --name moviepilot \
     --hostname moviepilot \
     -p 3000:3000 \
     -v /volume1/MoviePilot/media:/media \
     -v /volume1/MoviePilot/moviepilot/config:/config \
     -v /volume1/MoviePilot/moviepilot/core:/moviepilot/.cache/ms-playwright \
     -v /var/run/docker.sock:/var/run/docker.sock:ro \
     -e 'NGINX_PORT=3000' \
     -e 'PORT=3001' \
     -e 'PUID=0' \
     -e 'PGID=0' \
     -e 'UMASK=000' \
     -e 'TZ=Asia/Shanghai' \
     -e 'AUTH_SITE=iyuu' \
     -e 'IYUU_SIGN=IYUU49857T109461ae250f7af151e87e3493f9916fed0222c6' \
     -e 'SUPERUSER=admin' \
     -e 'API_TOKEN=moviepilot' \
     -e 'PROXY_HOST=http://192.168.3.48:7890' \
     --restart always \
     jxxghp/moviepilot:latest
`
