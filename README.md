# nmma-data

Vendored reference data for [NMMA](https://github.com/nuclear-multimessenger-astronomy/nmma) —
sncosmo bandpasses + SED models, dustmaps, etc.

Used by `nmma` as a git submodule:

```bash
git submodule add https://github.com/nuclear-multimessenger-astronomy/nmma-data.git nmma-data
```

CI points sncosmo at the vendored copy via `SNCOSMO_DATA_DIR`, so the test
suite never has to talk to `sncosmo.github.io` or the SVO filter service.

## Refreshing the cache

After installing sncosmo + dustmaps locally:

```bash
python tools/refresh.py                 # all categories
python tools/refresh.py --no-models     # bandpasses only (small + fast)
python tools/refresh.py --no-dust       # skip the SFD maps
```
