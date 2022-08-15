** Build **

> docker buildx create --use
> docker buildx bake --no-cache -f docker-compose.yml --set *.platform=linux/arm64,linux/amd64 --push