# OpenVaultDB demo Space for Listus

A small, fictional to-do and shopping database for the OpenVaultDB CLI demo.

The intended entry point is `ovdb demo serve --app listus`. It keeps your copy
under `~/ovdb/sneat/demo-space/` and serves it through a temporary authenticated
connection. The one-hour session ends automatically; local data remains.

This repository is a public seed, not a place for real user data. Never commit
credentials, cloud user or Space identifiers, endpoint addresses, or personal
lists here. Changes made while trying the demo stay in your local copy and are
not automatically pushed.

## What you will see

The **To do** list starts with `Tick me`, then
`Check changes in ~/ovdb/sneat/demo-space/`. The **To buy** list contains Milk,
Bread and Apples. In Listus, tick an item or add/edit one, then inspect
`lists/lists.yaml` in your local copy. Reloading Listus or restarting the demo
does not reset your changes.

The inGitDB storage engine commits successful writes locally. Inspect both the
files and `git log -p -1` to see the latest change; `git diff` can be empty when
the change has already been committed. Nothing is automatically pushed.

## Files and validation

- `ovdb.yaml` mounts this repository as database `demo-sneat-space`.
- `.ingitdb/root-collections.yaml` registers the `spaces` and `lists` collections.
- Each `.collection/definition.yaml` declares the readable YAML record format.
- `spaces/spaces.yaml` has the fictional `demo` Space; the real cloud Space ID
  belongs to your private registration, not to this seed.
- `lists/lists.yaml` stores the records `do:demo` and `buy:demo`. Keeping their
  IDs inside one YAML file avoids platform-specific filename restrictions.

With the inGitDB CLI installed, validate the seed or your local copy:

```sh
ingitdb validate --path .
```

The sample timestamps and creator values are fictional. No credential, real
user ID, endpoint or live session is included. The demo command is being
implemented; check the OpenVaultDB CLI release notes for availability.
