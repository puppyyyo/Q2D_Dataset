# Query-to-Document Legal Case Retrieval Dataset

This dataset contains legal judgments and query-retrieval pairs for multiple crime types.  
Each crime type is stored in a separate folder under `data/`, and all folders follow the same structure.

## Directory Structure
```bash
data/
├── forgery/
├── fraud/
├── larceny/
├── sexoffences/
└── snatch/
```

Each crime-type folder contains the following files and subdirectories:
```bash
├── corpus_all.json
├── format
│   ├── corpus.json
│   ├── qrels.json
│   └── queries.json
├── query_corpus_50.json
├── retrieve_corpus_500.json
└── summary.json
```

## File Descriptions
- `corpus_all.json`: The complete corpus containing all judgments.
- `query_corpus_50.json`: A subset of 50 judgments randomly sampled from `retrieve_corpus_500.json` to be used as queries. (Unprocessed)
- `retrieve_corpus_500.json`: A subset of 500 judgments randomly sampled from `corpus_all.json` to serve as the retrieval corpus.
- `summary_json`: Summarized facts extracted from each entry in `query_corpus_50.json`. (Processed)
- `format/`: Contains the standardized files formatted for retrieval tasks:
    - `corpus_json`: The retrieval corpus.
    - `queries.json`: Processed queries from `summary.json`.
    - `qrels.json`: Relevance annotations that indicate which documents are relevant to each query.