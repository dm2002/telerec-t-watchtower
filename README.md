# telerect-t-watchtower
Watchtower container for Telerec't modified by dm2002 because the original containerr/watchtower is no longer maintend. Switched to nickfedor/watchtower

* [docs](https://watchtower.nickfedor.com/)


To enable watching a container add the label:   
`com.centurylinklabs.watchtower.enable="true"`

To manually trigger a scan run, where `http_token` is whatever you set in `watchtower.http_token` (default=`abracadabra`)
```
curl -H "Authorization: Bearer {{ http_token }}" https://watchtower.example.com/v1/update
```

## Service config
  * `version`: Which version of [nickfedor/watchtower](https://hub.docker.com/r/nickfedor/watchtower) to use (default = latest)
  * `poll_interval`: Poll interval (in seconds). This value controls how frequently watchtower will poll for new images. See [docs](https://watchtower.nickfedor.com/v1.13.0/configuration/arguments/#poll_interval)
  * `http_token`: Api token for sending http requests to watchtower (see [docs](https://watchtower.nickfedor.com/v1.13.0/configuration/arguments/#http_api_periodic_polls)). HTTP API mode is only activated if this token is non-empty. 
  * `telegram_bot_token`
  * `telegram_channel_id`
