# Scoop bucket of Serhii Zhyhunenko

[![Tests](https://github.com/SerZhyAle/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/SerZhyAle/scoop-bucket/actions/workflows/ci.yml)

[Scoop](https://scoop.sh) manifests for the Windows programs of Serhii Zhyhunenko.

| Program | Install name | What it does |
| --- | --- | --- |
| [FileDO](https://serzhyale.github.io/FileDO/) | `filedo` | Tests USB sticks and SD cards for fake capacity, finds duplicate files, compares and copies folders, and wipes free space to make recovery harder. A window and a command line. |

## Install

```pwsh
scoop bucket add serzhyale https://github.com/SerZhyAle/scoop-bucket
scoop install serzhyale/filedo
```

`filedo_win` opens the FileDO window, and Scoop adds it to the Start menu as FileDO. `filedo` runs the same jobs in a terminal - for example `filedo E: test del` writes test files to the free space of `E:`, reads them back and deletes them.

Update with `scoop update filedo`, remove with `scoop uninstall filedo`.

The FileDO build is not code-signed: [what Windows may show, and why](https://serzhyale.github.io/FileDO/guides/install-trust.html).

## How the manifests stay current

Each program's own release script updates its manifest as part of every release: it writes the new version, download address and SHA256 into the manifest, and the SHA256 is read twice and must agree - from the `.sha256` file published beside the download and from GitHub's own digest of the download. Every commit here is then checked by Scoop's own manifest tests.

## Contact

Serhii Zhyhunenko, sza@ukr.net. A problem with a program itself goes to that program's tracker - for FileDO, [FileDO issues](https://github.com/SerZhyAle/FileDO/issues). A problem with a manifest goes to the issues of this repository.

## License

The manifests are in the public domain ([The Unlicense](LICENSE)). Each program keeps its own license; FileDO is MIT.
