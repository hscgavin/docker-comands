# docker-comands
Docker CLI commands you should know

## Containers

commands for containers: `docker container xyz_command`
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
### Start container
```bash
# Create a container from an image.
docker container create your_repo/your_image:your_tag

# Attach the container to STDIN, STDOUT or STDERR. -a is short for --attach.
docker container create -a STDIN your_repo/your_image:your_tag

# Start an existing container.
docker container start your_container_id_or_name

#Create a new container and start it.
docker container run your_repo/your_image:your_tag # run === create + start

# -i is short for --interactive. Keep STDIN open even if unattached.
# -t is short for--tty. Allocates a pseudo terminal that connects your terminal with the container’s STDIN and STDOUT.
# You need to specify both -i and -t to then interact with the container through your terminal shell.
# -p is short for --port. The port is the interface with the outside world.9000:8000 maps the Docker port 8000 to port 9000 on your machine.
# If you had an app that output something to the browser you could then navigate your browser to localhost:9000 and see it.
# --rm Automatically delete the container when it stops running.
docker container run -i -t -p 9000:8000 --rm your_image

# -d is short for --detach. Run the container in the background.
# Allows you to use the terminal for other commands while your container runs.
docker container run -d your_image
```
### Check container

```bash
# List running containers. Also provides useful information about the containers.
docker container ls

# -a is short for -all. List all containers (not just running ones).
# -s is short for --size. List the size for each container.
docker container ls -a -s

# See lots of info about a container.
docker container inspect your_container

# Print a container’s logs.
docker container logs your_container
```

### End container

```bash
# Stop one or more running containers gracefully. Gives a default of 10 seconds before container shutdown to finish any processes.
docker container stop my_container

# Stop one or more running containers abruptly. It’s like pulling the plug on the TV. Prefer stop in most situations.
docker container kill my_container

# Kill all running containers.
docker container kill $(docker ps -q)

# Delete one or more containers.
docker container rm my_container

# Delete all containers that are not running.
docker container rm $(docker ps -a -q)
```

## Images
`docker image xyz_command`
```bash
build # Build an image.
push # Push an image to a remote registry.
ls # List images.
history # See intermediate image info.
inspect # See lots of info about an image, including the layers.
rm # Delete an image.
```
