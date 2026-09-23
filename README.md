# shelf-data-template

Public default data folder for shelf-compose.

Default `data/` folder for
[shelf-compose](https://github.com/intisy-compose/shelf-compose), so a fresh
`git clone --recursive` runs out of the box.

It is mounted at `data/`: the db-backup sidecar writes its hourly database dumps to
`backups/` and Supabase Storage keeps shelf's uploaded files in `storage/`. Both are runtime state
and gitignored, so this template tracks no files of its own; the folders are created on first
start. The database itself lives in a Docker volume, and `backups/` is how it gets back.

## Use your own data

Fork or replace this repo, then point the folder at it from the shelf-compose checkout:

```powershell
.\docker-compose.ps1 data use <owner/repo[@ref]>   # your own data repo, optionally a branch
.\docker-compose.ps1 data use                      # back to this template
```

Commit configuration, not runtime state.

## License

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
