# Repolex Knowledge Graph of NousResearch/StripedHyenaTrainer

RDF knowledge graph data for [NousResearch/StripedHyenaTrainer](https://github.com/NousResearch/StripedHyenaTrainer), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/StripedHyenaTrainer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 288a526b8e265d4dfc58f6585fb127ba95c763b0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 288a526b8e265d4dfc58f6585fb127ba95c763b0
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 6864361eb350014e87bb5ee10e2bdde89df1d32d.nq.gz
│   ├── 761ca850a8fc9411d82cdd7987a97b9d8825cbf1.nq.gz
│   ├── c0879bc80263e85a02587280de1f2418ed3fcaec.nq.gz
│   └── dcc147f0d7ab417e25b76dde3e4b59bf30e0904e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 288a526b8e265d4dfc58f6585fb127ba95c763b0.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 11 files
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

[NousResearch/StripedHyenaTrainer](https://github.com/NousResearch/StripedHyenaTrainer)

---
*Parsed on 2026-10-09 by [repolex](https://repolex.ai)*
