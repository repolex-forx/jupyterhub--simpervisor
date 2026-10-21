# Repolex Knowledge Graph of jupyterhub/simpervisor

RDF knowledge graph data for [jupyterhub/simpervisor](https://github.com/jupyterhub/simpervisor), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/simpervisor
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 24730d8bf9574e1adfb755804882acedd3696855
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 24730d8bf9574e1adfb755804882acedd3696855
│           └── chunk-001.nq.gz
├── blob
│   ├── 07f19292811a3b690d5f9f3cf96bba22a7bca415.nq.gz
│   ├── 0a77e5b0cbd75c04b20808d768718f005bce30ce.nq.gz
│   ├── 0cf50603f7f3c415e346479534070b3d4d0cd043.nq.gz
│   ├── 14ef862524981bcfec0abc2ca2b1d5fd4284fb43.nq.gz
│   ├── 1aba38f67a2211cf5b09466d7b411206cb7223bf.nq.gz
│   ├── 1eb67ee436382638b99187e95d49ebf99f3e5139.nq.gz
│   ├── 1f807810c7535fa4a935bc4a86a875d8fe50bd6e.nq.gz
│   ├── 22ef1cd1ba592066c652c4f40eb71161872daad3.nq.gz
│   ├── 23c9aff9bfffee34343cd689676a7aa43850cacc.nq.gz
│   ├── 246a778090c0aaa0fd1ba743f916d1de5877ace5.nq.gz
│   ├── 30f2c93b1a5363443541be3bde3305e16cd245dc.nq.gz
│   ├── 3c4244e4fdb3b97c430ebc82d2284eabe74c61fe.nq.gz
│   ├── 6d9898b15d1fd6dadd0b417165324c10e75dfe49.nq.gz
│   ├── 70109e67dd6d303029ba781de1c948e5e62459ad.nq.gz
│   ├── 81ee46db29bb9cadb0e146474a5a8b9edd834c58.nq.gz
│   ├── 934be1e90ba6223be03fcee7ca2218ba5c3622c9.nq.gz
│   ├── 94e2fe18fe91c0870875a3a0f4d61500abe5628e.nq.gz
│   ├── a264e8ab08afce6b909e4416f617508ce7289405.nq.gz
│   ├── c09320edebfaa752f01f96d68da26ff50661ba8a.nq.gz
│   ├── c0dc11fede05aede401fb49f05f814d71811d202.nq.gz
│   ├── c3fcdf813c0e821a6bd6778b226dc219bf96777b.nq.gz
│   ├── c9721e0219967c57ef4310edf2671f92d81eac09.nq.gz
│   └── e9abeb232102cc287721aec0170e7c4c5dc28aa2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 24730d8bf9574e1adfb755804882acedd3696855.nq.gz
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

[jupyterhub/simpervisor](https://github.com/jupyterhub/simpervisor)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
