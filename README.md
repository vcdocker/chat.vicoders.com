# Vicoders Docker Rocket Chat

Vicoders docker stack with Traefik as proxy service and Rocket Chat

- [Vicoders Docker Rocket Chat](#Vicoders-Docker-Rocket-Chat)
  - [Overview](#Overview)
  - [Installation Guide](#Installation-Guide)

## Overview

This guide will show you how to set up Rocket Chat server with Traefik as a load balancer/proxy and Consul to store configurations and HTTPS certificates.

## Installation Guide

Deploy the stack with

```
docker stack deploy -c traefik.yml chat
```

Check if the stack was deployed with

```
docker stack ps chat
```

After mongo instance created, connect to mongo instance and run command

```
mongo mongo/rocketchat --eval "rs.initiate({_id: 'rs0',members: [ { _id: 0, host: 'localhost:27017'}] })"
```
