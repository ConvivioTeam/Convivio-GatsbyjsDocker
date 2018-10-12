# Convivio Docker for GatsbyJS

## Introduction

GatsbyJSDocker is a set of docker images for working with a [GatsbyJS](https://www.gatsbyjs.org/) site. Use the `docker-composer.yml` file to spin up a local development environment on your machine.

## Stack

The stack contains the following Docker images:

| Container         | Version           | Service name      | Image                         |
| -------------     | -------------     | ----------------- | -------------                 |
| GatsbyJS          | latest            | `gatsby`          | [gatsbyjs/gatsby]             |
| Portainer         | latest            | `portainer`       | [portainer/portainer]         |
| Traefik           | latest            | `traefik`         | [_/traefik]                   |

## Getting started

Assumes you have Docker running on your local machine.

1. Copy `.env.example` to `.env` and change any variables as necessary.
2. Your GatsbyJS site should be installed in the `./site/` directory.
  - See the [GatsbyJS docs](https://www.gatsbyjs.org/docs/) for getting started with a Gatsby site.
  - You may also like to clone your own Gatsby site to this location.
3. From the `./site/` directory build your gatsby site: 

```
$ gatsby build
```
The Docker image does not detect changes to your Gatsby site. You will need to rebuild your site yourself.


4. Your site should be available at your `$PROJECT_BASE_URL` location (default: [http://gatsbyjs.docker.localhost](http://gatsbyjs.docker.localhost)).


// TODO
The Nginx in the Gatsby container seems to be caching the HTML pages built by Gatsby. Even though they're mounted correctly into the container, and update after a `gatsby build`, the Nginx is still throwing out an old page. I wonder why.
