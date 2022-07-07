# docker-compose-node

Sample repo for https://youtrack.jetbrains.com/issue/WEB-56507/

Running the `dev` service via the CLI executes the JS code.

```shell
$ /usr/local/bin/docker-compose up dev
[+] Running 1/1
⠿ Container docker-compose-node-dev-1  Created                                                                                           
Attaching to docker-compose-node-dev-1
docker-compose-node-dev-1  | Hello World
docker-compose-node-dev-1 exited with code 0
```

Setting the `dev` service as a [Node.js Remote Interpreter][1] and running `index.js` via a Node
Run Configuration fails as the IDE attempts to download a non-existent image.

```shell
node /tmp/091c69d0-4293-4f62-a7f9-bcc878e571c0/index.js
[+] Running 0/1
 ⠿ release Error                                                                                                                         
Error response from daemon: pull access denied for doesnotexist, repository does not exist or may require 'docker login': denied: requested access to the resource is denied
```

[1]: https://www.jetbrains.com/help/webstorm/node-with-docker.html#ws_node_configure_remote_node_interpreter_docker_compose
