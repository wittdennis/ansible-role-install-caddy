# wittdennis.install_caddy

Role to install and manage a [Caddy](https://caddyserver.com) webserver.

## Requirements

- System with systemd

## Role Variables

```yaml
install_caddy_user: www-data
install_caddy_home: /home/caddy
install_caddy_version: v2.9.1 # Version of caddy to install
install_caddy_github_base_url: "https://github.com/caddyserver/caddy"
install_caddy_force_update: false # Set to true to always re-download caddy regardless if version matches or not
install_caddy_os: linux # os family of the target system
install_caddy_caddyfile: | # The caddyfile content
  http://localhost:2020
  respond "Hello, world!"
install_caddy_additional_args: "" # additional arguments to pass to the caddy execution
install_caddy_systemd_restart_startlimitburst: "5"
install_caddy_systemd_restart_startlimitinterval: "86400"
install_caddy_systemd_restart: "on-failure" # always, on-success, on-failure, on-abnormal, on-abort, on-watchdog
install_caddy_number_of_threads: 0 # Limits the number of threads. 0 = no limit
install_caddy_environment_variables: {} # Environment variables for the caddy process
install_caddy_environment_files: [] # Files with environment variables for the caddy process
```

## Dependencies

None.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: wittdennis.install_caddy, install_caddy_version: v2.9.1 }

## License

MIT
