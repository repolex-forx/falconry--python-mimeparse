# Repolex Knowledge Graph of falconry/python-mimeparse

RDF knowledge graph data for [falconry/python-mimeparse](https://github.com/falconry/python-mimeparse), parsed by [repolex](https://repolex.ai).

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
rlex download falconry/python-mimeparse
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 76d2173365410430e46864ebcbe1c335ad3ef0e3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 76d2173365410430e46864ebcbe1c335ad3ef0e3
│           └── chunk-001.nq.gz
├── blob
│   ├── 2ceee397eb4bf9f8c6bb64cb2d6ce6ec49922399.nq.gz
│   ├── 38186f505f2aa1df0d02cac8897be5bfb0b4c79d.nq.gz
│   ├── 3bdb9ab41983e521aa511e3a66e145584ae94deb.nq.gz
│   ├── 3da6188887847354bc240d0fd3b5b40d1023c7e1.nq.gz
│   ├── 5e413e3af3cf9af4054f9c0818e48504bb76ef0d.nq.gz
│   ├── 89de354795ec7a7cdab07c091029653d3618540d.nq.gz
│   ├── 91dde29e96f591056b4b57fbe088ea5ddf87f9a9.nq.gz
│   ├── a218b5529476d84d3749dc9a433b0b5b72ec1586.nq.gz
│   ├── d4c368307baf771705f88df2e72b0e19754a966e.nq.gz
│   ├── e2c32535cc366d77e936f57ed1559d1c04262ff7.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 76d2173365410430e46864ebcbe1c335ad3ef0e3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[falconry/python-mimeparse](https://github.com/falconry/python-mimeparse)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
