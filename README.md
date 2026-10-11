# Repolex Knowledge Graph of pallets-eco/flask-jsonschema

RDF knowledge graph data for [pallets-eco/flask-jsonschema](https://github.com/pallets-eco/flask-jsonschema), parsed by [repolex](https://repolex.ai).

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
rlex download pallets-eco/flask-jsonschema
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c3041bfebc67fe10489261f970b75e760174fa34
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c3041bfebc67fe10489261f970b75e760174fa34
│           └── chunk-001.nq.gz
├── blob
│   ├── 09c0f9aa6486f4537b2cfcade6525f1b505e50c7.nq.gz
│   ├── 23d1773c9bce8c85ef767ff6666d42ad93ca082b.nq.gz
│   ├── 2b1a4f0b9c203602ddb36d0d6ba3939d49e86e11.nq.gz
│   ├── 43a63d7c02adc3e982d33ff8c37c2ae80a12d27b.nq.gz
│   ├── 5def9259a4511649e033a6ba0c2e8e7152ccdfc9.nq.gz
│   ├── c36aa896f64b38267344628a4837b28ba6657a8b.nq.gz
│   └── e21cb29d775185d3ab5f44984b7fd28092ed3ab9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c3041bfebc67fe10489261f970b75e760174fa34.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[pallets-eco/flask-jsonschema](https://github.com/pallets-eco/flask-jsonschema)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
