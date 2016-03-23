# trinitronx/docker-cli53

[cli53][cli53-github] in a Docker container.  New GoLang build of [cli53][cli53-github], forked from [original build][zeitgeist-docker-cli53] of [alexzeitgeist/docker-cli53][zeitgeist-docker-cli53].

## Requirements

* [Docker](https://www.docker.com/) 1.5+ (previous versions may work fine, but I haven't tried)

## Installation

Get the [trusted build on the docker hub][trinitronx-docker-cli53]:

```bash
$ docker pull trinitronx/docker-cli53
```

or download and compile the source yourself from Github:

```bash
$ git clone https://github.com/trinitronx/docker-cli53.git
$ cd docker-cli53
$ docker build -t trinitronx/docker-cli53 .
```

## Usage

[cli53][cli53-github] is a command line tool to administer the Amazon Route 53 DNS service. Related instructions can be found on its project page. You need to pass your Amazon AWS credentials to the container either through environment variables as `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`, or by sharing your local `~/.aws/credentials` file as a volume. Example:

```bash
$ docker run --rm \
  -e AWS_ACCESS_KEY_ID="your aws access key" \
  -e AWS_SECRET_ACCESS_KEY="your aws secret key" \
  trinitronx/docker-cli53 list
```


```bash
$ docker run --rm \
  -v ~/.aws:/home/user/.aws \
  trinitronx/docker-cli53 list
```

[cli53-github]: https://github.com/barnybug/cli53
[zeitgeist-docker-cli53]: https://github.com/alexzeitgeist/docker-cli53
[zeitgeist-docker-cli53]: https://registry.hub.docker.com/u/zeitgeist/docker-cli53/
[trinitronx-docker-cli53]: https://registry.hub.docker.com/u/trinitronx/docker-cli53/
[trinitronx-cli53-github]: https://github.com/trinitronx/cli53
