# upCheck Roadmap

Generic systemd + URL up-checker plugin. Feature parity with monokit1 `upCheck/`.

## Scaffolding

- [X] Plugin skeleton from pluginTemplate (go.mod, justfile, Containerfile, test harness)
- [X] Example config `config/upcheck.yml`
- [ ] Config struct + `upcheck.yml` case wired into monokit_lib
- [ ] Podman integration tests

## Features

- [ ] Configured systemd units: alarm + Redmine issue when not active/installed, closed on recovery
- [ ] PostgreSQL unit special-casing (glob resolution of postgresql* units; dedicated issue when not installed)
- [ ] URL probes (method, expected status, timeout) with three distinct failure modes
  - [ ] Request-construction failure
  - [ ] Unreachable (timeout/network)
  - [ ] Unexpected status code
  - [ ] Per-URL Redmine issues with success/failure bodies
- [ ] Alarm/issue key sanitisation so unit names and URLs are safe as keys
- [ ] Health summary box output (depends on the lib renderer)
- [ ] Health data POST to the server API (depends on base client/server API)
