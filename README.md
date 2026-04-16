# Repolex Knowledge Graph of anthropics/claude-code-base-action

RDF knowledge graph data for [anthropics/claude-code-base-action](https://github.com/anthropics/claude-code-base-action), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download anthropics/claude-code-base-action
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e8132bc5e637a42c27763fc757faa37e1ee43b34
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── e8132bc5e637a42c27763fc757faa37e1ee43b34.nq.gz
│   └── repolex
│       └── e8132bc5e637a42c27763fc757faa37e1ee43b34
│           └── chunk-001.nq.gz
├── blob
│   ├── 02c8350960d051fdeb1cd58ade0a37c5bc797739.nq.gz
│   ├── 0967ef424bce6791893e9a57bb952f80fd536e93.nq.gz
│   ├── 0f2bb602624bf396afa7adf2a3a9dd74df842197.nq.gz
│   ├── 17f0af6661818584e70c8096125cb7059d6015ca.nq.gz
│   ├── 19cf0cd51417244961f0aea6e54aef6b7883a383.nq.gz
│   ├── 1d095b79daf084772f77d801abd2dd35873c3563.nq.gz
│   ├── 1d456dd7848e41dc2db5b1f46b62a6996717a89c.nq.gz
│   ├── 37b4f45abcbf73101e21a1382261311df8801e45.nq.gz
│   ├── 43ea427634270119aa6d697ee8f127d0f2cd22a9.nq.gz
│   ├── 4dc2592635379332d233abccb0c8a51d9e470ed7.nq.gz
│   ├── 60101a3c9e3793e1bf543296d240d384e66fbd00.nq.gz
│   ├── 6c40cfe2520a737eb811250660a4c59f33b138b9.nq.gz
│   ├── 6e48a6843a5d0b43c67563ae91850e077dadce37.nq.gz
│   ├── 74573995f9e5f620935ae61cb0716cce9b6c2238.nq.gz
│   ├── 754f704b1c1d943be92d080629a552dde50bceda.nq.gz
│   ├── 7dcfb18e97cbbabcf750d4982d9a4100e6a4e57d.nq.gz
│   ├── 863bf611721db3b90ef7fe06b223c319737f4f17.nq.gz
│   ├── 86be57f496ab5d76198988adbd6bf035e82d897e.nq.gz
│   ├── 919d2cde0f85d1fdc1f40536bc9d249f97990ebd.nq.gz
│   ├── a3639c72d5d0d81d874422c1481b51b3c4495f12.nq.gz
│   ├── a5f3924d4ec22752f312c6e5d61742ae96fd7e94.nq.gz
│   ├── ad75c9e774b8073e78474d009a7da582410a7d03.nq.gz
│   ├── c7eba19a0d12529d006b2b19af76c237084879db.nq.gz
│   ├── d38865be6d39deae94b07efd8c6bf3a6da5e8b3b.nq.gz
│   ├── d792193b867d80b341a2c50d4c7523ff3b6fb73f.nq.gz
│   ├── e59ed46f640483404ad32aa1d84bd231ae5d255e.nq.gz
│   ├── e8e2eb4f5eea46227b0bcb768f29ea3576b38a0f.nq.gz
│   ├── eac47d784f051f9d9e36edf6d12d19d1b09d1797.nq.gz
│   ├── eb9165e0c1653ab024ddf19b995e571f8f49009d.nq.gz
│   ├── edb7fd2cff027cb853da6d07c43f5a9ce0163c80.nq.gz
│   └── f4d37246dded2a46ddb14dd93d625579cc764083.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── e8132bc5e637a42c27763fc757faa37e1ee43b34.nq.gz
├── filetree
│   └── e8132bc5e637a42c27763fc757faa37e1ee43b34.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 41 files
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

## Source repository

[anthropics/claude-code-base-action](https://github.com/anthropics/claude-code-base-action)

---
*Parsed on 2026-04-16 by [repolex](https://repolex.ai)*
