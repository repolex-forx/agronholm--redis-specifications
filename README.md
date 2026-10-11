# Repolex Knowledge Graph of agronholm/redis-specifications

RDF knowledge graph data for [agronholm/redis-specifications](https://github.com/agronholm/redis-specifications), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/redis-specifications
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7bd21a07658a904b0507d808e52cbe7868cb5018
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7bd21a07658a904b0507d808e52cbe7868cb5018
│           └── chunk-001.nq.gz
├── blob
│   ├── 2788ed1b20e4a502a504ec33f075acddd1a5548a.nq.gz
│   ├── 2e9b6e890a6a04b54f804c5d00b6203be29ccd1a.nq.gz
│   ├── 392c94fc0f7607123faaee17268c59fb1fb124a3.nq.gz
│   ├── 3f27b8068f12148b3d8ff8d99073c23a71484ffd.nq.gz
│   ├── 49af88cfe01f283449e989813dd5acce974c365e.nq.gz
│   ├── 8cea3f29d3373b9f3c7be1891007d0b0ae450ffd.nq.gz
│   ├── a65ddc4f882eacaf71dd78609952e53b9d14792f.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7bd21a07658a904b0507d808e52cbe7868cb5018.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 14 files
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

[agronholm/redis-specifications](https://github.com/agronholm/redis-specifications)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
