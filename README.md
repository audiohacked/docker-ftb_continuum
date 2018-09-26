# Feed-The-Beast Continuum (Modded Minecraft Map 1.12) in Docker
To pull the image:
```
docker pull audiohacked/ftb_continuum:stable
```

It's highly recommended run a named data volume:
```
docker volume create minecraft_ftb_continuum_data
docker volume create minecraft_fftb_continuum_backups
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_continuum \
    --volume minecraft_ftb_continuum_data:/minecraft/world \
    --volume minecraft_ftb_continuum_backups:/minecraft/backups \
    --publish 25565:25565 \
    --env EULA=TRUE \
    audiohacked/ftb_continuum:stable
```
