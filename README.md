# `docker plugin` UX prototype

## [Proposal/Spec](https://docs.google.com/document/d/19pn5jQkY3rW5jp9_NFabAguIDXF_GpcG4iyNCkCdgFc/edit)

#### Requirements

 * Bash
 * [jq](http://stedolan.github.io/jq/download/)

#### Setup

 * Put `./docker-plugin` in your PATH
 * Run `docker-plugin` to display usage

#### Differences from proposal

 * Plugin containers are not hidden from `docker ps`
 * All options of `docker ps` are available to `docker-plugin ls`
 * Plugin containers are named in the format `plugin.<image-basename>`
  * Overriding name without `plugin.` prefix will break `docker-plugin ls`
 * No handshake performed, but `_handshake` env is set to "yes" or "no"
 * During upgrade, `docker pull` failure is ignored to allow local images
