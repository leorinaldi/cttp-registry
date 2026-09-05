# cttp-registry

The first cttp registry: one TOML pointer file per name under `names/`, and the first snippets
under `snippets/`. See the registry section of the
[cttp spec](https://github.com/leorinaldi/cttp/blob/main/docs/spec.md#8-the-registry).

**Claiming a name.** Put a `cttp.toml` at the root of the target repository declaring the name
(`name = "your-name"`, or `names = ["…"]` for several) on its default branch — that is the proof
of control — then run

```
cttp name claim your-name --target host/owner/repo/path/to/file.py --description "One line."
```

which opens a pull request here. The `verify` workflow checks the declaration, the owner, the
target and every label before it can be merged. `cttp name show your-name` prints the entry.
