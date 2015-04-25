# zeitgeist/docker-cli53

[cli53](https://github.com/barnybug/cli53) in a Docker container.

## Requirements

* [Docker](https://www.docker.com/) 1.5+ (previous versions may work fine, but I haven't tried)

## Installation

Get the [trusted build on the docker hub](https://registry.hub.docker.com/u/zeitgeist/docker-cli53/):

```bash
$ docker pull zeitgeist/docker-cli53
```

or download and compile the source yourself from Github:

```bash
$ git clone https://github.com/alexzeitgeist/docker-cli53.git
$ cd docker-cli53
$ docker build -t zeitgeist/docker-cli53 .
```

## Usage

[cli53](https://github.com/barnybug/cli53) is a command line tool to administer the Amazon Route 53 DNS service. Related instructions can be found on its project page. You need to pass your Amazon AWS credentials to the container either through environment variables as AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY, or by sharing your local ~/.boto file as a volume. Example:

```bash
$ docker run --rm \
  -e AWS_ACCESS_KEY_ID="your aws access key" \
  -e AWS_SECRET_ACCESS_KEY="your aws secret key" \
  zeitgeist/docker-cli53 list
```

```bash
$ docker run --rm \
  -v ~/.boto:/home/user/.boto \
  zeitgeist/docker-cli53 list
```
