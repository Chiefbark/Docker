# chiefbark/node

Ubuntu based image with git, node and npm installed.

Default node version: `lts`

If you want another version, do:

```
$ wget https://raw.githubusercontent.com/Chiefbark/Docker/master/node/Dockerfile
$ docker build -t <image-name> --build-arg node_version=<version> .
```

You can see the available node versions here:

https://github.com/nodesource/distributions#debinstall

Example:
```
$ docker build -t test-node --build-arg node_version=current .
```

## Usage

Start a container in interactive mode, and assign a volume (if needed).

This image exposes the port 3000 by default. Use `-p <port>:<port>` in the run command to modify this configuration.

```
$ docker run -it -v `pwd`:/usr/src chiefbark/node[:TAG]
```

Once you created the container, you will be prompted to create a new project.

Run `npm start` and open http://localhost:3000 to see the project or http://&lt;container-ip&gt;:3000.
<br>
(no source code included, so you may need to create an http server)

Run `docker inspect <container> | grep IPAddress` while the container is running to check the container-ip.