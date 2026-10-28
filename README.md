# openpeon-packs

Voice packs for [OpenPeon](https://openpeon.com/) (CESP v1.0), playable with [peon-ping](https://github.com/PeonPing/peon-ping) and other CESP players.

## Layout

One directory per pack. The directory name matches the pack's `name` in `openpeon.json`.

```
<pack-name>/
  openpeon.json
  sounds/
    *.mp3 | *.wav | *.ogg
```

## Pack rules (CESP v1.0)

- `name`: `a-z`, `0-9`, `-`, `_`
- Sound filenames: `[a-zA-Z0-9._-]`
- Formats: WAV, MP3, OGG Vorbis
- Max 1 MB per file, 50 MB per pack
- Every sound entry needs `sha256` for registry submission
- Categories: `session.start`, `task.acknowledge`, `task.complete`, `task.error`, `input.required`, `resource.limit` (core); `user.spam`, `session.end`, `task.progress` (extended)

Spec: https://github.com/PeonPing/openpeon/blob/main/spec/cesp-v1.md

## Publishing

1. Tag a release: `git tag v1.0.0 && git push origin v1.0.0`
2. Add an entry to [PeonPing/registry](https://github.com/PeonPing/registry) with `source_repo: krzysztofsurdy/openpeon-packs`, `source_ref: <tag>` and `source_path: <pack-name>`
