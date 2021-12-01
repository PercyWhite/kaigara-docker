** Build **

> docker buildx bake -f docker-compose.yml --set *.platform=linux/arm64,linux/amd64 --push