# Repolex Knowledge Graph of Pylons/pyramid_ldap

RDF knowledge graph data for [Pylons/pyramid_ldap](https://github.com/Pylons/pyramid_ldap), parsed by [repolex](https://repolex.ai).

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
rlex download Pylons/pyramid_ldap
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 02aec38c809e93b11f73051ffc0ae66f68fe8920
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 02aec38c809e93b11f73051ffc0ae66f68fe8920
│           └── chunk-001.nq.gz
├── blob
│   ├── 09e63bb36aafcc4af5e88b8633bb2d94bd9d94d8.nq.gz
│   ├── 0f978deba8603f2c1ed61bdddf0db4fe54e29632.nq.gz
│   ├── 142b6ca357fee89f09803fc9ad7ff676500c37cf.nq.gz
│   ├── 22f9f5b5799096e3f7bf3c7d75f6904ae1fdaed4.nq.gz
│   ├── 3e7677be85828f7350a74dffa7388234c188b27e.nq.gz
│   ├── 3fc0f11d5ba7105aa5fd7701b3acfba4719d7968.nq.gz
│   ├── 40b070cc7ba383766870a953c0ea5970761c4b18.nq.gz
│   ├── 43bb8a4c8d556be7e06237bd6680745ef1620034.nq.gz
│   ├── 48ceb978a7c3cbd9c14030ad311a76997248adfc.nq.gz
│   ├── 5ad1d252b78327d228e478435386420930e6948e.nq.gz
│   ├── 5ed96afe0e579496b448161799b4eab42a5df0e8.nq.gz
│   ├── 62121c4f15f4945cd12eb885c5904ae8aa5f3d80.nq.gz
│   ├── 6c406de5096abcf356847155cb93f4ee0aa15ee9.nq.gz
│   ├── 72d41600e6da418709e6f2bd19239f6f4fffe00d.nq.gz
│   ├── 8f44c854807edef401a1c24b03f43cce5476d64a.nq.gz
│   ├── 92dedcb76f52fd8a38d3399dab0ba9055916c4d9.nq.gz
│   ├── 95393465d86fda9fed4c35ce73c55e06f497ce6b.nq.gz
│   ├── a6f86bf77029f5ca1c28166ed57509034a859537.nq.gz
│   ├── acba20c8d7fe3b8c4fa35c8c7f05eb5cf9934da0.nq.gz
│   ├── b236f2976b44960a8ff885248c0799eb7aff4a47.nq.gz
│   ├── b44e2979203e492d03b2a6421ec433b3badf943d.nq.gz
│   ├── bb381fc539bf51f49a755277508637223b538f4e.nq.gz
│   ├── e002fbd7290a6a03cf1ed24d560931ed5af4974d.nq.gz
│   ├── e7ca0928a5134b681e9fe943e6e8a37ff6cc1e52.nq.gz
│   ├── ee2a941c44d6b708945e57046da0aad5239fe1c6.nq.gz
│   └── fcbc735be60b2d6b66f36aae402bd2b59759a99c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 02aec38c809e93b11f73051ffc0ae66f68fe8920.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[Pylons/pyramid_ldap](https://github.com/Pylons/pyramid_ldap)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
