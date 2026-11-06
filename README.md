# Ferret for Unraid

The Unraid Community Apps template for [Ferret](https://github.com/ferret-project/ferret), a self-hosted home inventory.

In Unraid: **Apps** → search for **Ferret** → Install. Before the first start, generate `AUTH_SECRET` and `FILES_KEY` in
Unraid's terminal (run it twice, one for each):

```sh
openssl rand -base64 32
```

Keep a copy of `FILES_KEY` in your password manager. Without it, uploaded photos and documents can't be read.

The container runs as `nobody:users` (99:100), like Unraid's shares. If Ferret's log says it can't write to its data
folder, run `chown -R 99:100 /mnt/user/appdata/ferret`.

Every AI feature is optional and runs on your own models. Set their addresses under **Show more settings**; the
help at `/docs` in Ferret covers each one.

- `templates/ferret.xml` — the template
- `ca_profile.xml` — this repository's page in Community Apps

Help: [issues](https://github.com/ferret-project/ferret/issues) on Ferret's repository, or
[Discord](https://discord.gg/XSkKyP2pdg).
