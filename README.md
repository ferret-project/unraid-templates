# Ferret for Unraid

The Unraid Community Apps template for [Ferret](https://github.com/ferret-project/ferret), a self-hosted home inventory.

In Unraid: **Apps** → search for **Ferret** → Install. Set `PUBLIC_URL` and start it: Ferret makes its own secrets
(`AUTH_SECRET`, `FILES_KEY`, the push keys) the first time and keeps them in its appdata folder. To set your own instead,
fill them in under **Show more settings** (`openssl rand -base64 32` each).

Once it runs, make a key file from the container's console and keep it off the server (Settings → Server → Keys shows
how). Without `FILES_KEY`, uploaded photos and documents can't be read.

The container runs as `nobody:users` (99:100), like Unraid's shares. If Ferret's log says it can't write to its data
folder, run `chown -R 99:100 /mnt/user/appdata/ferret`.

Every AI feature is optional and runs on your own models. Set their addresses under **Show more settings**; the
help at `/docs` in Ferret covers each one.

- `templates/ferret.xml` — the template
- `ca_profile.xml` — this repository's page in Community Apps

Help: [issues](https://github.com/ferret-project/ferret/issues) on Ferret's repository, or
[Discord](https://discord.gg/XSkKyP2pdg).
