# Dozable's recipe directory

This repository is the site behind **doz.sh**: Dozable's signed recipe catalogue.

- `v1/recipes.json` — the catalogue's manifest and its Ed25519 signature (Dozable's update key).
- `v1/recipes/<serial>/` — the files the manifest names, each pinned by sha256 and size.
- `v1/index.json` — a plain, unsigned index of the recipes, for the website and anyone else to read.

Every doz checks the signature, the serial and each file before it uses a catalogue; a catalogue that fails any check
is ignored whole. Nothing here is secret: it is signed, not encrypted. How and why:
[RECIPE-SIGNING.md](https://github.com/dozable/dozable/blob/main/docs/RECIPE-SIGNING.md).

The files are written by `make publish-recipes` in [dozable/dozable](https://github.com/dozable/dozable); do not edit
them by hand.
