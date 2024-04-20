# Vaultwarden Demo

You can run the compose file with docker.

```shell
docker compose up -d
```

The demo consists of

- [vaultwarden](http://localhost:8000) and
- [mailhog](http://smtp:pass123@127.0.0.1:8025)

There is no admin user in Vaultwarden. You need to go to http://localhost:8000/admin and use the password that was used
to generate the admin token. You find that in the `docker-compose.yml` file above the ADMIN_TOKEN.

In the admin interface you can invite users via e-mail.

HINT: The command to create the admin token based on a password is found in the `docker-compose.yml`. The result of that
command is a string that contains `$` characters. These need to be escaped by doubling them -> `$$`. If you don't do
that you will see some error messages on container startup and the admin token won't work.