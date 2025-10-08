# pve-spice-puller

> ***small daemon utility for tunneling spice configs to users***

## what

- reads .env for config
- exposes a webhook using tiny http
- sends GET to PVE instance when said webhook is POST'ed
- receives spiceconfig from PVE, drops it onto user in proper .vv format

## why

i needed a way to let my colleagues to connect to "airgapped" vms but didn't want to make a user for each one, looked for solutions, found not a lot

## danger

not to be used in any serious deployment, this thing is so unsafe i wonder how it even runs on rust

- tls is forcefully disabled
- a lot of unwraps
- written by an idiot

## usage

- pull
- populate `.env.template` with credentials and other info
- rename `.env.template` to `.env`
- run it as is with `cargo run` in detached state
- or `cargo build` and make a service out of this, i don't really care lol

> this was created out of desperation and boredom
