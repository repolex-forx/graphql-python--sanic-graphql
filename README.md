# Repolex Knowledge Graph of graphql-python/sanic-graphql

RDF knowledge graph data for [graphql-python/sanic-graphql](https://github.com/graphql-python/sanic-graphql), parsed by [repolex](https://repolex.ai).

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
rlex download graphql-python/sanic-graphql
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9eb1b0b4d4d8411833f3502a1bb659cf6ea58f88
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9eb1b0b4d4d8411833f3502a1bb659cf6ea58f88
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b9e5d3581960cd98338e6598fab0c95c716fac6.nq.gz
│   ├── 3f8ae569f6b8091c80896fc31883c5aacb1881ba.nq.gz
│   ├── 5170f738335f8e9f3445116122bb134b1d5911b1.nq.gz
│   ├── 5d09370e3de2a9a6ec100ba4f8b879e1c92167bb.nq.gz
│   ├── 60ecc750935b92e0a7b2e84c5fa765dc0eb369db.nq.gz
│   ├── 642f015bf654723c3863819074fc78c5dbe328a6.nq.gz
│   ├── 740697cc4feadae017c5895587967adcbfe3528c.nq.gz
│   ├── 7dafb35f2193f2f181a8c68819eccb5ddfed03a8.nq.gz
│   ├── 8040c5bb176790375e1d33e19d50886984849248.nq.gz
│   ├── 90a69f45ad6834d2c3c0f6365f17482001018f05.nq.gz
│   ├── 9d8ef0857c3fc9e3f9d77eb215de83e506f3ceaf.nq.gz
│   ├── b6ff2043f2cc918fa4bdf6f3de58edf53146f133.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f820941c54d44601b6523546665eb530a135b0f1.nq.gz
│   └── fb8acb1584dd0933537f9d8fe183cc679e997558.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9eb1b0b4d4d8411833f3502a1bb659cf6ea58f88.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[graphql-python/sanic-graphql](https://github.com/graphql-python/sanic-graphql)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
