# Deploy your Elixir/Phoenix app to a VPS

If a vps provider didn't have an aftermarket docker instance,  install docker

```bash
curl -sSL https://get.docker.com/ | sh
```

clone this repository

```bash
git clone https://github.com/jaeyson/deploy-elixir-app-to-vps app && cd app
```

then add/update `.env`

```bash
cp .env.example .env
```

change line 27 of `docker-compose.yml` from:

```yaml
    command: caddy reverse-proxy --from https://example.com:443 --to http://web:4000
```

to:

```yaml
    command: caddy reverse-proxy --from https://yourdomainhere.com:443 --to http://web:4000
```

then run it

```bash
docker compose up --build -d
```
