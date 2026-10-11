# Repolex Knowledge Graph of pydantic/files.pydantic.run

RDF knowledge graph data for [pydantic/files.pydantic.run](https://github.com/pydantic/files.pydantic.run), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/files.pydantic.run
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6254f2cfe90a583731b73ad48c9b396e49629719
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6254f2cfe90a583731b73ad48c9b396e49629719
│           └── chunk-001.nq.gz
├── blob
│   ├── 12ceaa361af4cc6c4ee8098097d5a79b5564dcef.nq.gz
│   ├── 5417ec130146eb124b97a135f2c27f739eb89cc8.nq.gz
│   ├── 8d8accc3b6f5fd5f81addc2cb33a60cb066dd5df.nq.gz
│   ├── 99971a9a445f8b210c1da669788d24b4a604d3fc.nq.gz
│   ├── cce84203f1adfa12536008a5148dbe8a563446ee.nq.gz
│   ├── d3b1bfdf70e1671fbadbe26081dc7d06c8db62f5.nq.gz
│   ├── dbebfae0d19fafcda40b1926de47e6345bdde6a4.nq.gz
│   ├── dd2f5882bbe734ef8bac9b565a436b13e877c714.nq.gz
│   ├── dfe8615c9b9cb5b080ca40c9322f0dcffb3b2f35.nq.gz
│   ├── e559da9dc778d1ce36cf86a62b5265f65bc62def.nq.gz
│   ├── e673150db0706f43ff67f6d8f6d21ec691911013.nq.gz
│   ├── f1accd58aef2171f1229afa18c23a57aabd951d3.nq.gz
│   └── f46002ab5cc956e44c0d684fad40e225ae1c37dd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6254f2cfe90a583731b73ad48c9b396e49629719.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 19 files
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

[pydantic/files.pydantic.run](https://github.com/pydantic/files.pydantic.run)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
