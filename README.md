# Repolex Knowledge Graph of jaraco/jaraco.vcs

RDF knowledge graph data for [jaraco/jaraco.vcs](https://github.com/jaraco/jaraco.vcs), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/jaraco.vcs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f33866f7c51a5561c4361ecf46fa3d1d353e628d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f33866f7c51a5561c4361ecf46fa3d1d353e628d
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b1542e1b83e39e6b9b21c470e5b49e33407d04d.nq.gz
│   ├── 10d412f406891b9683f832fcbc134c9bdf4f916e.nq.gz
│   ├── 17835dc8393986ed138639dacc8999761972b532.nq.gz
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 1fe6d24eb9cad858951e47fc7cf0ccfbda6b67e4.nq.gz
│   ├── 28a25aa6a2d05338dcbbf34dd6fd461cad501b91.nq.gz
│   ├── 28c746fc9177f0834c63382b46993dab14b91512.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 2f4e4c16a592e364112aff1175e047c4244ebf28.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 35a216b8c33a664d83b7715e70b334480d318d9a.nq.gz
│   ├── 4a62abfbd37803b583bba5fbccd41245034d038b.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 669fc829473ed718fa7950a3aa903aef4ffa5622.nq.gz
│   ├── 681209159c9d31e507b804cd8fea2cf31cae8656.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 70f04775ab6d038387741088edb4687e6e06f50c.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 7cbf5f67adfe71f3019756c97fe683e2a6c43831.nq.gz
│   ├── 8a21e73df1cb5b6245b2f53cf30e6baddbb1c146.nq.gz
│   ├── 93aef42f44cdc36cadcf333a936d6e73e76987f1.nq.gz
│   ├── 9a0f3bce1395ae3819030b822e5d9076c85068ea.nq.gz
│   ├── 9f073471489b4e4664f7e0ebaa266d9142a7a96d.nq.gz
│   ├── d4fad4a18d480e23529e273b5c00c22a751885a2.nq.gz
│   ├── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── fc7f61672bc0f0ad742013b74d89ac117a749cd7.nq.gz
│   ├── fd18bb8a8ed5a3a5fe91ccdb753f2694bd202db5.nq.gz
│   └── fe68ac575f99a55b85cbac54f2dd7b589eb750ff.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f33866f7c51a5561c4361ecf46fa3d1d353e628d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 40 files
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

[jaraco/jaraco.vcs](https://github.com/jaraco/jaraco.vcs)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
