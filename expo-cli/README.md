# chiefbark/expo-cli

Ubuntu based image with git, node, npm and expo-cli installed.

## Usage

Start a container in interactive mode, and assign a volume (if needed).

⚠ This image does not expose any port. Connect the container to your host network to access the expo devtools (default port 19002).

```
$ docker run -it -v `pwd`:/usr/src -w /usr/src --network=host chiefbark/expo-cli[:TAG]
```

Once you created the container, you will be prompted to create a new expo project.

Run `npm start` and open http://localhost:19002 to see the devtools of the project or http://&lt;container-ip&gt;:19002.

Run `docker inspect <container> | grep IPAddress` while the container is running to check the container-ip.

### Variables --build-arg

| var | default | description |
|:--|:--|:--|
| NODE_VERSION | `'lts'` | node version. See https://github.com/nodesource/distributions#debinstall. |