# chiefbark/node

Ubuntu based image with git, node and npm installed.

## Usage

Start a container in interactive mode, and assign a volume (if needed).

This image does expose the port 3000 by default. Use `-p <port>:<port>` in the run command to modify this configuration.

```
$ docker run -it -v `pwd`:/usr/src chiefbark/node[:TAG]
```

Once you created the container, you will be prompted to create a new project.

Run `npm start` and open http://localhost:3000 to see the project or http://&lt;container-ip&gt;:3000.
<br>
(no source code included, so you may need to create an http server)

Run `docker inspect <container> | grep IPAddress` while the container is running to check the container-ip.

### Variables --build-arg

| var | default | description |
|:--|:--|:--|
| node-version | `'lts'` | node version. See https://github.com/nodesource/distributions#debinstall. |