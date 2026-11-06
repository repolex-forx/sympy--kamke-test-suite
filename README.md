# Repolex Knowledge Graph of sympy/kamke-test-suite

RDF knowledge graph data for [sympy/kamke-test-suite](https://github.com/sympy/kamke-test-suite), parsed by [repolex](https://repolex.ai).

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
rlex download sympy/kamke-test-suite
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4a23fb7db23de5027ed8dae4e79efa56c6e337bb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4a23fb7db23de5027ed8dae4e79efa56c6e337bb
│           └── chunk-001.nq.gz
├── blob
│   ├── 711f4022dcba0c1878424f934be1d95646e9ab9c.nq.gz
│   ├── 853403ba0a2ce8b753a2a245744bc2296f1c7a39.nq.gz
│   ├── 87519a6dda453c0f2fb208647864a5abe4b5da6c.nq.gz
│   ├── d7b5d624d75cd0a7c45e599afd7c202ce403796d.nq.gz
│   └── ffc7f1061626c6340fba0161dfcee60d7b879f19.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4a23fb7db23de5027ed8dae4e79efa56c6e337bb.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 11 files
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

[sympy/kamke-test-suite](https://github.com/sympy/kamke-test-suite)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
