# xhgui-docker

[![Release version](https://img.shields.io/github/release/cv21/xhgui-docker.svg)](https://github.com/cv21/xhgui/) [![Docker pulls](https://img.shields.io/docker/pulls/cv21/xhgui.svg)](https://hub.docker.com/r/cv21/xhgui/) [![Docker stars](https://img.shields.io/docker/stars/cv21/xhgui.svg)](https://hub.docker.com/r/cv21/xhgui/)

Docker image allow to you use xhgui as service inside its own container. 
Just provide your data provider to container's mongo instance.

## Table Of Contents
- [Usage](#usage)
    - [Executing as part of compose of containers](#executing-with-docker-compose)
    - [Executing as standalone container](#executing-as-standalone-container)
- [Roadmap for 1.0 version](#roadmap-for-1.0-version)

## Usage

### Executing with docker-compose

1. Configure your [docker-compose.yml](https://docs.docker.com/compose/compose-file/)

    ```
    version: "2"
    services:
        web: ...
        backend:
            ...
            links: [db, xhgui]
        db: ...
        xhgui:
            image: cv21/xhgui
            ports: 
                - 8081:80
    ```

2. Build
    ```
$ docker-compose build .
```

3. Run
    ```
$ docker-compose up -d
```

4. Open xhgui (as described in docker-compose.yml on port 8081 http://127.0.0.1:8081) and see results

TODO: Describe the docker-compose example for nginx-php-xhgui set of containers

### Executing as standalone container

1. Execute docker image
    ```
$ docker run -p 8081:80 cv21/xhgui
```

2. Open link http://127.0.0.1:8081

## Roadmap for 1.0 version

- [x] Allow to use xhgui codebase by in-folder code
- [ ] Update docs
- [ ] Allow to use configs