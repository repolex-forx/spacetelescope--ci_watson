# Repolex Knowledge Graph of spacetelescope/ci_watson

RDF knowledge graph data for [spacetelescope/ci_watson](https://github.com/spacetelescope/ci_watson), parsed by [repolex](https://repolex.ai).

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
rlex download spacetelescope/ci_watson
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d6fa926e4750ab777084454b1d0d50631ab8eda6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d6fa926e4750ab777084454b1d0d50631ab8eda6
│           └── chunk-001.nq.gz
├── blob
│   ├── 047a9f677f4d045c7314a766c37ab0fef11bb5fa.nq.gz
│   ├── 0deb0f602b18ae95df345c7ccdadeefa6ed6e80c.nq.gz
│   ├── 282ada3c6782688e602acade930c1fdd755c4aa9.nq.gz
│   ├── 2a36bedfd40c75ea754b2033f2c509fb3f824c47.nq.gz
│   ├── 2fca14933e46761ede57f99896a98074609ed2c3.nq.gz
│   ├── 385fe9a78ae979504420d266e2bf6f950d67e42c.nq.gz
│   ├── 43d403964a4fefed0882b17e860c2e4e358b2d2f.nq.gz
│   ├── 5005f8573de360489f79f17c206b894096f3f348.nq.gz
│   ├── 595563f2f4d9f45a065947862db9415a9ce4f416.nq.gz
│   ├── 5a8b56b31746f8aab87b9fd97da80b16c1224f5f.nq.gz
│   ├── 5b181d03de915cd95f80704832f6f82926797973.nq.gz
│   ├── 64baff93e55015e4bba983ed972e76f222dde745.nq.gz
│   ├── 6b0c235992bd42858029a97cf48d4950a1438b9a.nq.gz
│   ├── 6e4b17ea317e9819f4bc9644d33d737ff8d0dd4d.nq.gz
│   ├── 74438d3e177b6f049e965d2a4effb23df4936c73.nq.gz
│   ├── 7f9cdf817aba5b456ca0333f6a54bb2d9d6a1d3c.nq.gz
│   ├── 83b229be3593791785653c204855fae87acdd1b4.nq.gz
│   ├── 8b0ed30afaaffc2701ccff0508ac4c949cf2c73d.nq.gz
│   ├── 8e896f21bcd78075a0b9d20ba8753faff83e7108.nq.gz
│   ├── 934d6125a44a17e60a8a8f6997e9a4a85cb6f941.nq.gz
│   ├── 9ed9ec3cb63096b3c65c730218829aa13ef2e8f1.nq.gz
│   ├── a5023e5fc32e2208db53aa199c13aa8297742b89.nq.gz
│   ├── a6ddb27051e319fb9dad8f0bf71d921a44df22ae.nq.gz
│   ├── ab8e5ff6ccaba7882473f5b2598831b9edf52f24.nq.gz
│   ├── ac846336d7167e8bc727ca94c315b6b01871f73f.nq.gz
│   ├── b9387f4006b8254a2273593043422111deaa2140.nq.gz
│   ├── c1b9abd0b6e3eb1f707e61b474e957918ba6853f.nq.gz
│   ├── c838f5bfddb4f4b67965f81a81fbcf45e879344d.nq.gz
│   ├── cc48b711b0a33016583c094ff390206cd7415422.nq.gz
│   ├── d34a7c3eb3b58a3a53532e97eb3040af28d869af.nq.gz
│   ├── d8034c07a110307d4f6d1a1df8a4a0481b15be8b.nq.gz
│   ├── da4df3cf8d9469f5e872582a0bb5b605c4409163.nq.gz
│   ├── e4b03da37d11da3f7644687d6ffbde147e004530.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e8f04b85bf455ecd408ba5d0f8a2993fd5780768.nq.gz
│   └── ebfc6acccab0d10ba8aed9bbd07cb38b0305c113.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d6fa926e4750ab777084454b1d0d50631ab8eda6.nq.gz
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

[spacetelescope/ci_watson](https://github.com/spacetelescope/ci_watson)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
