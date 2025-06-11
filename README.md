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

## Example

`corpus.json`

```json
{
    "id": 0,
    "text": "臺灣臺中地方法院刑事簡易判決104年度審簡字第896號公訴人臺灣臺中地方法院檢察署檢察官被告游麗華上列被告因偽造文書案件，經檢察官提起公訴（104年度調偵字第21號），因被告於本院訊問程序就被訴事實為有罪之陳述（104年度審易字第1476號），本院認為宜以簡易判決處刑，裁定逕以簡易判決處刑，判決如下：主文游麗華犯使公務員登載不實文書罪，處拘役伍拾日，如易科罰金，以新臺幣壹仟元折算壹日..."
}
```

`queries.json`

```json
{
    "id": 0,
    "text": "被告明知詐欺集團成員，仍介紹未成年人參與詐欺，提供聯絡工具協助冒用公務員名義詐取財物。"
}
```

`qrels.json`

```json
{
    "qid": 0,
    "docid": 466,
    "relevance": 1
}
```