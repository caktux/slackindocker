Docker container for [slackin](https://github.com/rauchg/slackin)
===

### Installation
```
git clone https://github.com/caktux/slackindocker
```

### Configuration

Copy `config.sample` to `config` and edit to your liking.

### Building and running

Build the docker container and run it with:

```
cd slackindocker/docker
docker build -t slackin .
docker run -d -t slackin
```

Enjoy :)
