# Kong & Konga Docker-Compose

Kong is easiest to use when paired with GUI management interface. This FLOSS pairing works well and can be scaled in an enterprise environment.

*Auto-scaling is WIP and will be added soon.

# Setup


## Token Secret
Edit the `docker-compose.yml` file to change following line with your _Token Secret_.

```Dockerfile
- "TOKEN_SECRET=SuperSecretLongPhrase" # Change this before running
```

This should be something like

```Dockerfile
- "TOKEN_SECRET=881da2b9000b7b9f3c62ef3750a22c5ec0f5db759ddd347fb0aab6488bf1ffc7"
```

## Ports

Adjust the ports exposed on the host machine by the service in the `docker-compose.yml` file.

```Dockerfile
- "8000:8000/tcp"
- "8001:8001/tcp"
- "8443:8443/tcp"
- "8444:8444/tcp"
```

\* _The left number is the host machine port, the right number is the container port, the last part is the packet type allowed to pass._ `host:container/packet_type`

# Starting

To start the service run the following in the `/` root directory.

```Bash
docker-compose up -d
```