# Docker Buildkite Plugin

A simple [Buildkite](https://buildkite.com/) Docker plugin allowing you to run a command in a Docker container. If you need more control, please see the [docker-compose Buildkite Plugin](https://github.com/buildkite-plugins/docker-compose-buildkite-plugin).

## Example

The following pipeline will run `yarn install` and `yarn test` inside a Docker container using the [node:7 Docker image](https://hub.docker.com/_/node/):

```yml
steps:
  - command: yarn install && yarn run test
    plugins:
      docker#v0.0.1:
        image: "node:7"
        workdir: /app
```

## Configuration

### `image`

The name of the Docker image to use. For example, `node:7`.

### `workdir`

The working directory where the pipeline’s code will be mounted to, and run from, inside the container. For example, `/app`.

## License

MIT (see [LICENSE](LICENSE))