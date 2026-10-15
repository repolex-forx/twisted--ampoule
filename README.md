# Repolex Knowledge Graph of twisted/ampoule

RDF knowledge graph data for [twisted/ampoule](https://github.com/twisted/ampoule), parsed by [repolex](https://repolex.ai).

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
rlex download twisted/ampoule
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 58d3003cc80ec5b66196ab7fc84e6edd075599f8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 58d3003cc80ec5b66196ab7fc84e6edd075599f8
│           └── chunk-001.nq.gz
├── blob
│   ├── 031598949b5b97c8206440fd0ab7ff4d2f51965c.nq.gz
│   ├── 12f8054a1ab87d10a9e7fa4fc5e3976a97eebe0f.nq.gz
│   ├── 13efc05ffd8af8a1967a29dcffd6e67b0bedc82c.nq.gz
│   ├── 15ccab4c2d009fcf8357d4e3765efc566475146f.nq.gz
│   ├── 1acbbb651e5bfcc1eed44babf52250bae7f8eec2.nq.gz
│   ├── 2f72fd233a4f5e61593f854581f433a02c11ad43.nq.gz
│   ├── 3d7f552f6bb5a2d00b8a27a84a8279b0de002f6c.nq.gz
│   ├── 3d90cd96d2cc598c02cbf637a8500690610cdd96.nq.gz
│   ├── 41d36a7baefcdc30cbde478166cf6b225fe0b068.nq.gz
│   ├── 617a529ff95d9c82a05ae23c053dbcf7970e769d.nq.gz
│   ├── 628d389ebded9b8716ef217b710cd216f36064f6.nq.gz
│   ├── 63dcbffa9a5c7c68426d079bf18922b69f82df88.nq.gz
│   ├── 6e8e65a4cf206797d0250ba70dd6e646a0f8c702.nq.gz
│   ├── 738e5f2edd579d66f788676d32ac4e9673b65b7d.nq.gz
│   ├── 7b005aaf08b096ebf8b685d039ad77030bc74ec2.nq.gz
│   ├── 89d86c8ac40a9215e48ad61d6d8a0f21c1f9b621.nq.gz
│   ├── 9313b59b84031f68e4054d0d65781d2ced9208cf.nq.gz
│   ├── 9a310ff891a1d8e5fbd860ba1c06e513a05db6e2.nq.gz
│   ├── 9ee78eb17a0339e48a0e19c52defadc07604566a.nq.gz
│   ├── ac3484bb4447dd4856f8392cbe9cd873cb1f7083.nq.gz
│   ├── ac3ed00bfd2d9a25b08630a7f7777ddcc51cfd7c.nq.gz
│   ├── ca25cb72f9bcdbc954b573f29cacbcb48b8b69f8.nq.gz
│   ├── caa3e0142ae39881fbbfee702de822a1b86ed64c.nq.gz
│   ├── cd67d6a953bb15c558626c715cd077ffb45b9719.nq.gz
│   ├── d19d78480f804e56c8bb7aa5940c9f7df844790c.nq.gz
│   ├── d3ddf0332ebfb2dfa8272d7db3dc06d5f00680a8.nq.gz
│   ├── db9d7dd16bdfca339ff2a186d86be5656abc7adc.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e6adfc1378b5fe9a2c3bb8ab394ee78cb06edef6.nq.gz
│   ├── f428adc5d4edeafe1fd39607b2ce196274d6c25d.nq.gz
│   └── f74c7e0f29d9badd2c50685c4495548f07d53f51.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 58d3003cc80ec5b66196ab7fc84e6edd075599f8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[twisted/ampoule](https://github.com/twisted/ampoule)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
