# docker-comands
Docker CLI commands you should know

### Containers
`docker container xyz_command`
 ```bash
create # Create a container from an image.
start # Start an existing container.
run # Create a new container and start it.
ls # List running containers.
inspect # See lots of info about a container.
logs # Print logs.
stop # Gracefully stop running container.
kill # Stop main process in container abruptly.
rm # Delete a stopped container.
```

### Images
`docker image xyz_command`
```bash
build # Build an image.
push # Push an image to a remote registry.
ls # List images.
history # See intermediate image info.
inspect # See lots of info about an image, including the layers.
rm # Delete an image.
```
