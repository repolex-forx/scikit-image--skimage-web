# Repolex Knowledge Graph of scikit-image/skimage-web

RDF knowledge graph data for [scikit-image/skimage-web](https://github.com/scikit-image/skimage-web), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download scikit-image/skimage-web
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6cfc7a586b4a58c4c20a5aa967b20a6bb72d2b59
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6cfc7a586b4a58c4c20a5aa967b20a6bb72d2b59
│           └── chunk-001.nq.gz
├── blob
│   ├── 13c26c91ea6d8c129df54b5969db0953469cbac6.nq.gz
│   ├── 176ab33e44dbb8e017679d9db2a739fdbd6cd4dc.nq.gz
│   ├── 1a1e3a75c77283c36e002b18319d5bb9005658e8.nq.gz
│   ├── 218e0b21e2c8ec1bddd076ee69301723f9a41fc6.nq.gz
│   ├── 22bdf89abbc8b1d8f9501c1ee07fd64ffa8db077.nq.gz
│   ├── 2cd68e5fed685eec881acfa888ff638ea780f495.nq.gz
│   ├── 32598271f0c087a93c2cd831e3dc2952e4278ce7.nq.gz
│   ├── 35c54c2a2fa5ba33a07d0d500dd6918d8519d3c6.nq.gz
│   ├── 37a97895651e01ec97968a4d143596b4ae3c2459.nq.gz
│   ├── 3bf6484a29d8da269f9bc874b25493a45fae3bae.nq.gz
│   ├── 43e2fb978f9dc259473f761b7e727e0d8c2f5e94.nq.gz
│   ├── 4615d4dee9f199da685c7741a783280b1cdb6969.nq.gz
│   ├── 51bc56e9f2b611f73176f2bbe2806dca00f518b6.nq.gz
│   ├── 532caa617753fb4d0791fc99cdfcb63784233ee9.nq.gz
│   ├── 62fbf6fdbc5373614079fd5a2da1e2fe050a9885.nq.gz
│   ├── 6f72eb809c491d7bfb62867dd55a3ac1094c13ba.nq.gz
│   ├── 7d17b3bdc64ce398bc3d2369c8d8685f44405071.nq.gz
│   ├── 7e0ed7bd96bdd75e2bf364882db861e2b6981474.nq.gz
│   ├── 8cbcb50510338f5f6ca76748f8ecc95e00269738.nq.gz
│   ├── 978324ef05185ee4f40512d1c3d711a8c132213a.nq.gz
│   ├── a4097e5efa67c3c694dde0460daebf02801e4538.nq.gz
│   ├── a9969993201f9cee63cf9f49217646347297b643.nq.gz
│   ├── b8e4b4a319a44776baaacccf4dc77db47f1b0faf.nq.gz
│   ├── bae285c4e0426e263638966337e5aa2c5f3498e9.nq.gz
│   ├── d0d2c89cbf8249c1bcd296796ab04daf7d23177a.nq.gz
│   ├── d54a6a1220da33d0b238b095323ec4f10c1dade4.nq.gz
│   ├── d93e2ed0e5752e27c96c455005c7e67bfbbc1d6d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── efc123f9ed2098970c04b6cca0c00e143e6a5444.nq.gz
│   ├── f186a08bac739180989cea5cbd6dc25503e70dc4.nq.gz
│   ├── f31aa37567c2185368cd9c392bce0920f3e75bd5.nq.gz
│   ├── f7a5a9bf84acfc1eada1ea6cb9eb2efeba1a855c.nq.gz
│   ├── fbb264a34300c5904088919084561d11b63daa76.nq.gz
│   └── fc87ecd4fd046aa1c2919964a3442b404a982694.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6cfc7a586b4a58c4c20a5aa967b20a6bb72d2b59.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[scikit-image/skimage-web](https://github.com/scikit-image/skimage-web)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
