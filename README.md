# Repolex Knowledge Graph of simonw/datasette-atom

RDF knowledge graph data for [simonw/datasette-atom](https://github.com/simonw/datasette-atom), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-atom
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 907ddfa520dd438a0181eb100954c6ac2de04265
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 907ddfa520dd438a0181eb100954c6ac2de04265
│           └── chunk-001.nq.gz
├── blob
│   ├── 147ae7eddef9fda2344591d50a37b3096aca8bf4.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 34b363914b95a4a21ffca8cbd76f52a6df486529.nq.gz
│   ├── 7f79551eee874c7628191dade934772c8adbd880.nq.gz
│   ├── a147c1f755684f8189aed9b36db01e0937ea2f3c.nq.gz
│   ├── a56f8faa6635f51e1ae95c825e465c5fabf07e52.nq.gz
│   ├── a897056cb516f610be2c2b13522abbe66668f379.nq.gz
│   ├── e0438b1dfa11fc2a6b043ead453d397cda939210.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 907ddfa520dd438a0181eb100954c6ac2de04265.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[simonw/datasette-atom](https://github.com/simonw/datasette-atom)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
