# Notify Push service

Prepare your setup:
* Setup your server with https.
* Install `notify_push` app.
* Start `push` alongside the other services:
  ```
  docker compose up nextcloud proxy push
  ```

Configure `notify_push` on the nextcloud instance:
* Configure the `notify_push` url:
  ```
  ./occ notify_push:setup http://push:7867/push
  ```
Once `notify_push:setup` finishes you can test the setup:
```bash
./occ notify_push:self-test
```

## Fixing problems:

If the version does not match:
  * Alter `docker/push/Dockerfile`.
  * Rebuild the image (`docker build .`).
  * Replace the push image in `docker-compose.yml`.
  * Tear down and restart the push service.

