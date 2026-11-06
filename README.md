# Repolex Knowledge Graph of sphinx-contrib/packages

RDF knowledge graph data for [sphinx-contrib/packages](https://github.com/sphinx-contrib/packages), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/packages
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── eda29dca967fa759936c3ea544c2f132125c10d1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── eda29dca967fa759936c3ea544c2f132125c10d1
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ab084a8424c48dfc74c67241d93674fa21c42d6.nq.gz
│   ├── 1096ec7387329007a9086e04ec802de55986e200.nq.gz
│   ├── 151168d7c3f14954972ac31a64c3c21c19fb89e8.nq.gz
│   ├── 1d9ceeba64f8e4cd1553cf6fa3c8033eea9fe94d.nq.gz
│   ├── 325e9996a697ad4917710e700790c8ed07db05d0.nq.gz
│   ├── 34d6a5c68de40fb8a3f0409def787ac225f0bd59.nq.gz
│   ├── 480c8e3d17ce255d74212404ff39ef8b7ebc89a3.nq.gz
│   ├── 4beb373e1ed0a390f52b1fdcc5c2123525083bfc.nq.gz
│   ├── 55779763e7f4617ae5910f4ebbbbcfe5e5816abe.nq.gz
│   ├── 611a819da3c795ab1f57308bad9708685720ff4f.nq.gz
│   ├── 688c192d109ec3b71bea92532e69e968da4edbf8.nq.gz
│   ├── 6994baeaf1ab35dcc549915dd63366861ba3d088.nq.gz
│   ├── 6a30e70007d2bea9de972380bbf53d154fc7007a.nq.gz
│   ├── 83bdf90b8c51dbbe7bc6b74e4fad0cb9d06b12b8.nq.gz
│   ├── 9a79e8a6379401c376565e87e6af6ed61273a711.nq.gz
│   ├── a3d29958529e0f3124b0a75cc830059c90c18fa9.nq.gz
│   ├── a485625d427fe22dc5597483e2581751cc127516.nq.gz
│   ├── b00bee6af237296dc3364999ccbb2789f33990ab.nq.gz
│   ├── b4169b6f8b962effc9d34bdbd605b58a86dd7867.nq.gz
│   ├── b59ba18fede0419d1fae85fa6b64b8bf7b28d12a.nq.gz
│   ├── b79c9457ab9cff68efb52dba00ab5b497c2b927b.nq.gz
│   ├── c44e49b096557f515f00280fd81cc64a55184a7c.nq.gz
│   ├── c563950bfb53f382331f1eb00916c2706d95c479.nq.gz
│   ├── c5e93448a08158e91bd88c11f64d187b9b19adbf.nq.gz
│   ├── cd9777ac39e66437611b7371e01835ebda412035.nq.gz
│   ├── cf27f2b0b77435600b1851623888d76bf30dddda.nq.gz
│   ├── d4731f8b55446d568f1de4298b427b1d4c1a983e.nq.gz
│   ├── dba13ed2ddf783ee8118c6a581dbf75305f816a3.nq.gz
│   ├── df261310482f2eee775de1a32186779f943aa87c.nq.gz
│   ├── eefc7946629489ce9c2f468ac5094d6e2f4f841c.nq.gz
│   ├── f7466804ca477da6c3d4bda53c888453a92b0fdf.nq.gz
│   ├── fac1473b1b8e4908352a34b95408c7d74102f82e.nq.gz
│   ├── fb8f97ac655b39763b697aa47f337819f2131526.nq.gz
│   ├── fd4f122ae7a96408fd1e061cc0b8009cde060949.nq.gz
│   └── ff02fd01094c72b560382f8d802e0eb6809a6620.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── eda29dca967fa759936c3ea544c2f132125c10d1.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 42 files
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

[sphinx-contrib/packages](https://github.com/sphinx-contrib/packages)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
