# Repolex Knowledge Graph of dtolnay/itoa

RDF knowledge graph data for [dtolnay/itoa](https://github.com/dtolnay/itoa), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/itoa
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── af77385d0daf4d0e949e81f2588be2e44f69f086
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── af77385d0daf4d0e949e81f2588be2e44f69f086.nq.gz
│   └── repolex
│       └── af77385d0daf4d0e949e81f2588be2e44f69f086
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 2342153b148d7fd7918bc4866b06329f6f92b21c.nq.gz
│   ├── 2b5e899121a1399ab10312dfdb9b0c989260d719.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 47a6144998bfa1ee7886be12cadf4766478d557e.nq.gz
│   ├── 4bc31dc394135fc1aa166b499d5f346bc0abfc2d.nq.gz
│   ├── 6b7c03d4052033e67411720d6f97faf3dfa00324.nq.gz
│   ├── 74cd9b4abab9aa160b740ca2d90402859e51387f.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 866a7334df8f6439bbc454092091b046992a8b60.nq.gz
│   ├── bfd3192d1f11be43593e2074e26653f946e1c4c8.nq.gz
│   ├── c4f0617c56496f25a272a5ee86a83ce5da7df2d7.nq.gz
│   ├── c5392026b5d1e7247187804003f09a72894e90ea.nq.gz
│   ├── cd2f848ad098cf275c4e0c37685f1474f40aecfc.nq.gz
│   ├── d8bd99aac1fe04b718d8e43873d317015661864a.nq.gz
│   └── e9e21997b1aca0707f8749ea13c09aec66c899d2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── af77385d0daf4d0e949e81f2588be2e44f69f086.nq.gz
├── filetree
│   └── af77385d0daf4d0e949e81f2588be2e44f69f086.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 26 files
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

[dtolnay/itoa](https://github.com/dtolnay/itoa)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
