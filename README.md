Caddy with cloudflare container for docker and podman
=====================================================

* Add cloudflare api token as needed
* Update LANDOMAIN and TSDOMAIN environment variables as needed


## Podman

* Update volumes as needed

```
printf "CLOUDFLARE_API_TOKEN" | podman secret create CLOUDFLARE_API_TOKEN -
cp caddy.container $HOME/.config/containers/systemd/
```

```
systemctl --user daemon-reload
systemctl --user enable --now caddy.service
```


## Docker

~~~
micro CLOUDFLARE_API_TOKEN
docker compose -f compose.yaml up -d
~~~
