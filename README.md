# Repolex Knowledge Graph of klen/muffin-jinja2

RDF knowledge graph data for [klen/muffin-jinja2](https://github.com/klen/muffin-jinja2), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-jinja2
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8c270cf7cfce7ee718e6629ad62add9bebdef747
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8c270cf7cfce7ee718e6629ad62add9bebdef747
│           └── chunk-001.nq.gz
├── blob
│   ├── 017e7d8bf62c2b57c1f52ae8b8fb1caf5d7475af.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 2a53bbce61ac32501175071328f39a9e19d1c803.nq.gz
│   ├── 374896cdccf72924772f3a74aa5f825b92be541b.nq.gz
│   ├── 3b38d52213e80cce01a8b8e0994ef396ad5ac4fc.nq.gz
│   ├── 3d3de9177b065ccd2b82e03a2cd70dd8b0e5323a.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 6e358b344df51dcf1a96b5d640af53bad957e581.nq.gz
│   ├── 754af8e7fcff24e89212afe05db0f0681270dfb4.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 7cae9e0ccf94f3ed18a22607e5e7168a73f03a79.nq.gz
│   ├── 7d35011a36af5133b48eb51528e2779de180eed6.nq.gz
│   ├── 80826d975aa6e305dddbe44be4b9e7ea0ca1dd87.nq.gz
│   ├── 9dc7557db40f666ebc81762c6ba39fbc493f4a22.nq.gz
│   ├── b7b880fb6d8b725f3820019756ec787e4a972c9f.nq.gz
│   ├── c3b5ab05b61c11cfe6f60a275299ec085f02e594.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── dcadb3a068ab1f7c35d42cf4fa3de78f6c0cbe16.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8c270cf7cfce7ee718e6629ad62add9bebdef747.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[klen/muffin-jinja2](https://github.com/klen/muffin-jinja2)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
