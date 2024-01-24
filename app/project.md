## Networking issue:
Error on `fly deploy`:
```
==> Building image
WARN Failed to start remote builder heartbeat: failed building options: failed probing "personal": context deadline exceeded
Error: failed to fetch an image or build from source: error connecting to docker: failed building options: failed probing "personal": context deadline exceeded
```

Fixed here: https://community.fly.io/t/eror-failed-to-start-remote-builder-heartbeat-failed-building-options-failed-probing-personal-context-deadline-exceeded/10708/2

Using: `fly wireguard reset`

## Fly syntax change
Dodds info was outdated. Had to run:
`fly volume create data -r dfw -n 1` to create the volume, not `fly vol create data --size 1`.
This error was rcvd: 

```
Error: Process group 'app' needs volumes with name 'data' to fullfill mounts defined in fly.toml; Run `fly volume create data -r REGION -n COUNT` for the following regions and counts: dfw=1 
```
