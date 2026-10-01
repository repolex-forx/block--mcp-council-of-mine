# Repolex Knowledge Graph of block/mcp-council-of-mine

RDF knowledge graph data for [block/mcp-council-of-mine](https://github.com/block/mcp-council-of-mine), parsed by [repolex](https://repolex.ai).

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
rlex download block/mcp-council-of-mine
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 03543f47f1f9783571bef57d10cd18eb17985e85
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 03543f47f1f9783571bef57d10cd18eb17985e85.nq.gz
│   └── repolex
│       └── 03543f47f1f9783571bef57d10cd18eb17985e85
│           └── chunk-001.nq.gz
├── blob
│   ├── 005619bb7afb40389ee903bcba3d30600280fda9.nq.gz
│   ├── 0ba9db25329d0b336e39ca8cde8470c5b7bc45eb.nq.gz
│   ├── 1bc469e68eb776aa52185c6cbfc5cdcaee837ce3.nq.gz
│   ├── 1cad0d1fbe8bb5bf62282f42d3c9bb3fff570291.nq.gz
│   ├── 1cd4d9d826b768995f14a194e156731fa7fc1484.nq.gz
│   ├── 25f0bc5ed80683a81f46e6bfd1cf8ea0b56c6807.nq.gz
│   ├── 26990a14244cdb93c107dcef90cfce7b343ddfde.nq.gz
│   ├── 29fc85c0c24603bac59cad4a7db296b9809b4adf.nq.gz
│   ├── 37d0958a96398d453cd661b9c01ad4e0d549cac8.nq.gz
│   ├── 3a89e3af3ceed914aa33b304cccccbf8917eb602.nq.gz
│   ├── 460b14c709e2776288cbeb2d8416f0f60827a1ba.nq.gz
│   ├── 4b1dbfeec26c5e7112d76400cb99f6d03b368416.nq.gz
│   ├── 517e1057ad5f202d088eabafc5bff24b5206697e.nq.gz
│   ├── 57655294960c09a217b4030d5a23188e623bcbfb.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 63357a1a863cc7872a6666ccacbbd76914407968.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 71a2d65af5ed3e5dc450efad9bbb6529e91f28ce.nq.gz
│   ├── 73961bfa8a33770ae204723248b0977577f6c391.nq.gz
│   ├── 8093ff64ebf70451f0e6c5574dbf82ba45b028a5.nq.gz
│   ├── 83b44d1d16b97d67f5c5be0d563e81158061f079.nq.gz
│   ├── 9582fc588754f78d9875691a3bd5e674295436b3.nq.gz
│   ├── 9863d42556571c6827b74699caadb3cc966d3026.nq.gz
│   ├── 9a8e9febe05eaaf8488ab402461aab783c314ad8.nq.gz
│   ├── 9f762e362030f5429a10f1e821b030f93222eee4.nq.gz
│   ├── a4a811756d4535ebf79e4812997fd29b3b1183f5.nq.gz
│   ├── a5529418e97365d721ce8f8e35712d7ce9f5d6dc.nq.gz
│   ├── a5650f399fb3f52aaf9a41c1ffdab738dda889a6.nq.gz
│   ├── a83d05041b75aabaf13ef70c82c245ea5800596e.nq.gz
│   ├── aba8834e880ece064fc31f0cee1f12f80558d2ff.nq.gz
│   ├── c6bb8b993b37794bac7a4e2e04b28d56ae72375e.nq.gz
│   ├── d67ad33d5e7784d2583fa3bc744da09b25d11f51.nq.gz
│   ├── e4de9b61ecde4431fe328851ce4e43f2b09e72c8.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e9b821177aa4bf9c42ec5ad99d141f58ed9b099e.nq.gz
│   └── eefa2e742ca02dd4470e3a711c1792d4ab783d4e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 03543f47f1f9783571bef57d10cd18eb17985e85.nq.gz
├── filetree
│   └── 03543f47f1f9783571bef57d10cd18eb17985e85.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 46 files
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

[block/mcp-council-of-mine](https://github.com/block/mcp-council-of-mine)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
