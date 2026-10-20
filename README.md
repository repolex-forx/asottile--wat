# Repolex Knowledge Graph of asottile/wat

RDF knowledge graph data for [asottile/wat](https://github.com/asottile/wat), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/wat
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5157ec1e646da2cace68cfeac506918aef815105
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5157ec1e646da2cace68cfeac506918aef815105
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d20b6487c61e7d1bde93acf4a14b7a89083a16d.nq.gz
│   ├── 0db2f5dafe71029b035066b46b0f46a148aa29ec.nq.gz
│   ├── 2b2356710eb6d9b5b5ab44f2f9d655ed24a460f9.nq.gz
│   ├── 3be8e39a705ef9b279b88ab808ebc3d8063fde81.nq.gz
│   ├── 496f09aff2e176cf6171b2fcc4e4d2abe576fedb.nq.gz
│   ├── 532e43f517936f38a113cbfe361563de2699a0d4.nq.gz
│   ├── 614b859443ff9ee3d9d6f816f1de71d3ef1f60f1.nq.gz
│   ├── 67dde70fc97e1b611440cc4e43f2457d914e8927.nq.gz
│   ├── 7032a03d038acce1614324acb9cb48f7e8fdd24e.nq.gz
│   ├── cbc0eb77e1dbcc517b764dd815d8b94099ab6eaa.nq.gz
│   ├── d830fe3cd4588a85f4729f66568daf68156fd4a6.nq.gz
│   ├── da7f5849045ada0f62d67f2a875e868b7b451909.nq.gz
│   ├── e53b87e7ed23866a92edc36b3d52b301aba22476.nq.gz
│   ├── f85ccddbb08914470a9d6ea4b2ab077650fcffbc.nq.gz
│   ├── f8fc383aca6be8f83603dd777f4a371a96433e9b.nq.gz
│   └── fe39d0ecb85f1ea335271f154fde6bb88caa3b6c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5157ec1e646da2cace68cfeac506918aef815105.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 23 files
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

[asottile/wat](https://github.com/asottile/wat)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
