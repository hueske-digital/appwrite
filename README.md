```
https://appwrite.patrickhilker.de {

    # import logging
    # import cloudflare
    import tls
    import compression
    import header

    reverse_proxy appwrite-traefik:80
}
```

# Upgrade Appwrite (for this repo!)

From `~/services` execute

```sh
docker run -it --rm \
    --volume /var/run/docker.sock:/var/run/docker.sock \
    --volume "$(pwd)"/appwrite:/usr/src/code/appwrite:rw \
    --entrypoint="upgrade" \
    appwrite/appwrite:1.4.4
```

Then review `docker-compose.yml` and `.env`:

```sh
diff .env.example .env
```
