# Repolex Knowledge Graph of rustls/tokio-rustls

RDF knowledge graph data for [rustls/tokio-rustls](https://github.com/rustls/tokio-rustls), parsed by [repolex](https://repolex.ai).

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
rlex download rustls/tokio-rustls
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f8832d28ce5688f101368e34fc6b49899a8d4293
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f8832d28ce5688f101368e34fc6b49899a8d4293.nq.gz
│   └── repolex
│       └── f8832d28ce5688f101368e34fc6b49899a8d4293
│           └── chunk-001.nq.gz
├── blob
│   ├── 2154394052ab5ff4ccfd1d3f2b19a6c94c164ad8.nq.gz
│   ├── 3e5e7f8834acf9c64bc731385897457d1bd8c147.nq.gz
│   ├── 3eb9271c89ffdaa8d1f5df88d80145b2957cd541.nq.gz
│   ├── 3ec91deb62aed4d690cc0f8294d9d01a5e559e42.nq.gz
│   ├── 4500636cd8a4f4ac4f7e0f787103b7ca3f9768f4.nq.gz
│   ├── 46c8a74b1461b1b003bcdc9b853f24afb44fc312.nq.gz
│   ├── 4c2c0ca4842558ec41a6c947e6ae6955893401ea.nq.gz
│   ├── 5997715cf7ea8a1e52b090344d0fdcfb5bbe67be.nq.gz
│   ├── 5d1e59d160aa02a52e26de8414a47cf2d1d805aa.nq.gz
│   ├── 748388f57b03041a35fabd3c3c98fc1a04f667b0.nq.gz
│   ├── 8c6fd795a8afe56a5349a449d36e5b92589ba0f9.nq.gz
│   ├── a0ce3fc09c8ba58af919ecd2c2bd487fb8dc3592.nq.gz
│   ├── a772c00b5dbd31b8919f6d5ba817798963ba6fa0.nq.gz
│   ├── ab5d19595d8429ff94dd95b2dea261c114e5f07e.nq.gz
│   ├── adcd3df610f426d7bb8cf70a976a721b5e98e057.nq.gz
│   ├── be70cafdca3555f0608946e24e40e1d3ac8d178a.nq.gz
│   ├── c4143cf75f10364e3080528f3b0246bb8a6450da.nq.gz
│   ├── c4e2c9c7e6d85d3371b3feaad46ddded5bc8f7ac.nq.gz
│   ├── c680bd8f0a7a89e1f698796916ee75c1338bd7a7.nq.gz
│   ├── da0cd4b37df03824bd5c4fd36deee2f89afc5976.nq.gz
│   ├── da50fc4e22cdc1a0d179a196a4c57e01099975fe.nq.gz
│   ├── e64cb05b4d63abebbe9655356bcc271e82950844.nq.gz
│   ├── e962b9e8bc5f4ff228413b458d5df489ec3ca593.nq.gz
│   ├── ede69d9b5c96c55867a70a1777447ca361ebdd1e.nq.gz
│   ├── f2b22bdc96c94910f026706f4695f9374860e7f7.nq.gz
│   └── f93217eaf819d59a0cd5cc468544673106b53747.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── f8832d28ce5688f101368e34fc6b49899a8d4293.nq.gz
├── filetree
│   └── f8832d28ce5688f101368e34fc6b49899a8d4293.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 36 files
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

[rustls/tokio-rustls](https://github.com/rustls/tokio-rustls)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
