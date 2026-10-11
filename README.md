# Repolex Knowledge Graph of cherrypy/cherrypy.github.io

RDF knowledge graph data for [cherrypy/cherrypy.github.io](https://github.com/cherrypy/cherrypy.github.io), parsed by [repolex](https://repolex.ai).

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
rlex download cherrypy/cherrypy.github.io
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 188d9e3db530f3897be3a379e386aa1d2498c5cf
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 188d9e3db530f3897be3a379e386aa1d2498c5cf
│           └── chunk-001.nq.gz
├── blob
│   ├── 1258eef7b213953d7cc1b695c081110a5e813fe8.nq.gz
│   ├── 27c305fa529fb29b2ca70593eb5d6a754cadf8fa.nq.gz
│   ├── 306d2a42392e86a7f7313edcab602876409a241c.nq.gz
│   ├── 40482d5a02d90ef1ed44c73835e0beefdb157ff9.nq.gz
│   ├── 4877557841d03f7e22a0cc24a42aef3ab4738140.nq.gz
│   ├── 919a56efbcd4d1330c1f50bd9ddcce0b61b16059.nq.gz
│   ├── d228e0b26768bdf817843dde8e60fb3f3ede567e.nq.gz
│   ├── d93d6f22c324aeb64fd15947e506f5fd7cad73e0.nq.gz
│   └── fd233c010f486405deec894896543eb93e2648f0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 188d9e3db530f3897be3a379e386aa1d2498c5cf.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[cherrypy/cherrypy.github.io](https://github.com/cherrypy/cherrypy.github.io)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
