# NeoForge 26.3 server

On the QNAP: upload this folder to `Container/minecraft`, then paste `compose.nas.yaml` into Container Station → Applications.

- Start: `docker compose up -d`
- Logs: `docker compose logs -f mc`
- Console: `docker exec -it <container> rcon-cli` (container name from `docker compose ps`)
- Add a mod: add its Modrinth slug to `MODRINTH_PROJECTS` in `compose.yaml`, then `docker compose up -d`
- Change a config: edit it in `./config`, then `docker compose restart mc`
- Restore:
  1. `docker compose stop`
  2. `tar -xf backups/<file>.tar.zst -C data/`
  3. `docker compose start`
