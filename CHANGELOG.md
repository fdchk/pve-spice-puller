# Changelog

## 0.1.0

initial release because i was bored out of my mind

### added

- webhook that receives GET and talks to PVE spiceproxy
- generates `.vv` files for virt-viewer
- config via `.config` file
- github actions that don't do much

### known issues

- everything

---

## 0.2.0

tls is no longer a joke (mostly)

### added

- tls verification is now enabled by default using system CA certificates
- `ca-cert` field in `.config` to point to your PVE's self-signed CA cert
- `--no-cert` flag to disable verification (with a warning, don't @ me)
- `--config <path>` flag to specify config file location
- `rustls-native-certs` for loading system certs instead of the unused native-tls

### removed

- `native-tls` dependency (was never used, lol)
- the `DANGER DANGER DANGER TODO: FIX THIS SHIT SOMEHOW` comment (finally)

### changed

- tls provider stays on rustls but now actually verifies certificates
- default behavior changed: verification on, system certs loaded
- error messages now include actual error details instead of silent panics
