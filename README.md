# Repolex Knowledge Graph of python-poetry/semver

RDF knowledge graph data for [python-poetry/semver](https://github.com/python-poetry/semver), parsed by [repolex](https://repolex.ai).

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
rlex download python-poetry/semver
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7ef69b00f6bd63539eb01ea8a947ca99a11fde93
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7ef69b00f6bd63539eb01ea8a947ca99a11fde93
│           └── chunk-001.nq.gz
├── blob
│   ├── 06831f6deb1e29555a64290d2f3fcd6a3e9b7125.nq.gz
│   ├── 1365ebdfe4e7af58a9907dd441f35d965f8b69b5.nq.gz
│   ├── 143dbd2e4633bdda1fde3434240079d81a97c33e.nq.gz
│   ├── 2a969b4e1909a02d2b595a15a00b99a6f64ecb20.nq.gz
│   ├── 2b36cd140e65999d24cabc84e7a4c8fe69c20be5.nq.gz
│   ├── 38d1806471996825d38bccb10b223559e694f4ec.nq.gz
│   ├── 3c5e27e10272f008fa03b0c3ecf992ace819cf1b.nq.gz
│   ├── 4adfb4b373b1886e783b13c43850c6e5843e5e5a.nq.gz
│   ├── 56aa236e4f912f8daa347131553b44cb0af37fde.nq.gz
│   ├── 63cce5487d5db052164193df70628f4da7c338e9.nq.gz
│   ├── 8f61aba136d6b51668f975af6ba88830269b6e8c.nq.gz
│   ├── 97fd82b0c5987f2683b4de06c233ed17cd0aab40.nq.gz
│   ├── af7dd784631878d623f0238677bc08b5cca5aec5.nq.gz
│   ├── ccccd1f29fb23a3ed1b759b845d16eda039035ed.nq.gz
│   ├── dd969722c90939b78631ace44c4defeb2040f280.nq.gz
│   ├── e4808b72bda902cec5633180ad3da30db5144527.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── efe869f1638da78f9ef281e0acff320cf79178d9.nq.gz
│   ├── f0eab0db7ea7183100628a27bb8b748c2afddc03.nq.gz
│   └── fb7a5f92400bf61998be56c81f16fe49086e1a1f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7ef69b00f6bd63539eb01ea8a947ca99a11fde93.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[python-poetry/semver](https://github.com/python-poetry/semver)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
