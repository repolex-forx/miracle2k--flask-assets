# Repolex Knowledge Graph of miracle2k/flask-assets

RDF knowledge graph data for [miracle2k/flask-assets](https://github.com/miracle2k/flask-assets), parsed by [repolex](https://repolex.ai).

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
rlex download miracle2k/flask-assets
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 62efd23fe95ee6a86fc1cfaa98fc1e2152093557
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 62efd23fe95ee6a86fc1cfaa98fc1e2152093557
│           └── chunk-001.nq.gz
├── blob
│   ├── 000c59f74862f17b24ad7a55daf9c6390399fb04.nq.gz
│   ├── 01fd422e2688b65440a7be441bd3ef52ae32780e.nq.gz
│   ├── 0450ffdddd165e7228f3343323d65bca9cbd530a.nq.gz
│   ├── 1207ee4d9a24d4219676b4e229305984b5439510.nq.gz
│   ├── 22d78c57e48749e048dff13d182e2e78c6dc846f.nq.gz
│   ├── 2c8a0267c712d34e5c7f84b5191f0479fd61c175.nq.gz
│   ├── 31840dfa0ea5887d410f874931fdd73517bed259.nq.gz
│   ├── 37938383e7b9f691f1ad5fa231211e63db2bec5d.nq.gz
│   ├── 3afecb14e6983e924e5481a207672b98f4c3a993.nq.gz
│   ├── 4717ad4b94f6dfedd27029b8432f7e5a458597a8.nq.gz
│   ├── 4c932f3e45efe89fc5e57c39f0b27cd5099b82d5.nq.gz
│   ├── 557ba8b11bd2a582ab9f61a3c77e69313288f576.nq.gz
│   ├── 5a579e169b1f32cf58e3948db704cb5d351d7017.nq.gz
│   ├── 62defb56898028a263e5d0043c8873e54e38a3bc.nq.gz
│   ├── 8ef8282a13f969d3a9e4ee6ccbf77d1569e4e05c.nq.gz
│   ├── 99c7a0373cc3875a8fafdc14140ce920c424040e.nq.gz
│   ├── 9d79475686f28bedc906c542431fe3fe8674ec75.nq.gz
│   ├── a5fad43ac990dd8084addc38c2be3abcac93002b.nq.gz
│   ├── a8c8cb74e8e03612b599ddc1abb055bd28fe3f5b.nq.gz
│   ├── aece12e319eac78c5ac77a7e6e208f908ef1b77c.nq.gz
│   ├── b7bf7f6d3ca17c9426d4572238df6db280bf5482.nq.gz
│   ├── ba70844f5c850b64a5ca2d0d42b9bb431b696331.nq.gz
│   ├── c3637a7cfcc7ac94a6447f341b60665b84bafff6.nq.gz
│   ├── c499e87220aa6ceac7541907bb7ffa18e93d32e9.nq.gz
│   ├── c5837220483d55769b3896fcedf3573ac02498cd.nq.gz
│   ├── c7c835e019587faa3acdbed3802674220ddc7a19.nq.gz
│   ├── c8864235684fe0525db5b541559e56a2980b66b8.nq.gz
│   ├── d58573256bff9794b1a15daf3d5128c36178a500.nq.gz
│   ├── e4fad03d4ed0fb81d806cb21eb091f83e01c89f2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb81a55426291960272cb4258dc8a8521383aa5a.nq.gz
│   ├── f3093c4bb6c43940c54a302b2322dfd8b2c6fa42.nq.gz
│   ├── f7026c974c3993fff430887cfc9cd650ace09f87.nq.gz
│   ├── f9e089dac3cebdafe7d5bfcb843e0b7173ac586d.nq.gz
│   ├── fb789a6f52dfc3aaffe5533dfc9be8f3b13c9966.nq.gz
│   └── ff535251f8612c1d2a5e1e8e236ed49fd3dfcc78.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 62efd23fe95ee6a86fc1cfaa98fc1e2152093557.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 44 files
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

[miracle2k/flask-assets](https://github.com/miracle2k/flask-assets)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
