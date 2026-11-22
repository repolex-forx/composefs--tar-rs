# Repolex Knowledge Graph of composefs/tar-rs

RDF knowledge graph data for [composefs/tar-rs](https://github.com/composefs/tar-rs), parsed by [repolex](https://repolex.ai).

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
rlex download composefs/tar-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4b095c863c04ef10b3a79beed8ecb481c469353b
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4b095c863c04ef10b3a79beed8ecb481c469353b.nq.gz
│   └── repolex
│       └── 4b095c863c04ef10b3a79beed8ecb481c469353b
│           └── chunk-001.nq.gz
├── blob
│   ├── 03df836450a264398bae00161952270e939a7901.nq.gz
│   ├── 0d1c96c0cfbb09ce8f0efcd16ad7d90c63d2697b.nq.gz
│   ├── 0e9cff900124c3fb80313778332decac722e7515.nq.gz
│   ├── 0f69abe898118e53d12cc5f8de06537f533fbdf3.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 1a77a79a0bd19b8948541ba2e14f90a1c1093fde.nq.gz
│   ├── 2fce07fc2a2578a51b87edfc8150df09e2f9c99d.nq.gz
│   ├── 336a5c3af1bf96467b122afd92bf0a3cc53c23fe.nq.gz
│   ├── 39e0ed6602151f235148e6c08413aa7eda5b9038.nq.gz
│   ├── 48d4cf9fd4ef0168667ee00b4980be2c08482a83.nq.gz
│   ├── 4fffb2f89cbd8f2169ce9914bd16bd43785bb368.nq.gz
│   ├── 67e79ffdfe2d85519305dff62a70a9950058a1d1.nq.gz
│   ├── 68e2a519eebd0d751f17106db3a5722cfc76f223.nq.gz
│   ├── 6d876964de56f2503d64e33f5c40c54fb3b1dbcb.nq.gz
│   ├── 6de2d3bd35786d6cc4319404f6825c9baa874dbc.nq.gz
│   ├── 747ddf9d585753b8e6acf36086270a3523c56ab8.nq.gz
│   ├── 8e1d7e05368bb4a6d55c778a800790a4d9a19384.nq.gz
│   ├── ac508defbb8cf1c6fdbee809acb6e633ee00b580.nq.gz
│   ├── c8a99af074d431ba35236f50dc351c709376ae5a.nq.gz
│   ├── d39beaa28d648db0e23a64dbc5bdd278feaf40ad.nq.gz
│   ├── d4f727435261fa154b62d3d85a2fe8cf70422dc3.nq.gz
│   ├── dd1c8a9fd5611c88405a307af267a15b302b8970.nq.gz
│   ├── e2cd61d322a4fa282aa559a1cb20d285d2dee049.nq.gz
│   ├── ec6867a4be3a84766e2b4d9dc8903abc66187359.nq.gz
│   ├── f9533b4997fa27f02f92d9154c1f99e2e1de0aa3.nq.gz
│   └── fc19b9d01a7cd6a3134b649faceb634e605ec22c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 4b095c863c04ef10b3a79beed8ecb481c469353b.nq.gz
├── filetree
│   └── 4b095c863c04ef10b3a79beed8ecb481c469353b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 36 files
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

[composefs/tar-rs](https://github.com/composefs/tar-rs)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
