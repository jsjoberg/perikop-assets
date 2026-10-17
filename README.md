# Perikop assets

Release storage for [Perikop](https://github.com/jsjoberg/perikop): CI dependency snapshots and voice packs.
They live here so that Perikop's own newest releases are only versions and nightlies, which the in-app updater reads.

- `ci-dependencies-<commit>`: offline CI inputs prepared from Perikop's pinned upstreams. Perikop's `ci/dependencies-lock.json` names the active one.
- `kokoro-sv-…`: prepared Swedish voice packs, pinned by hash in Perikop's `ci/upstreams.json`.

To prepare a new dependency snapshot from a Perikop commit or branch:

```sh
gh workflow run dependencies.yml --repo jsjoberg/perikop-assets -f ref=main
```

The workflow logic is [`dependencies.yml` in Perikop](https://github.com/jsjoberg/perikop/blob/main/.github/workflows/dependencies.yml).
