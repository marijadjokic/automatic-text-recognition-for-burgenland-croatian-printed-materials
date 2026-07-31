# Burgenland Croatian - Evaluation Results

This repository contains the evaluation results of the model **["Burgenland Croatian Typewritten 2010-2019"](https://www.transkribus.org/models/burgenland-croatian-typewritten-2010-2019)** available on the [Transkribus](https://transkribus.eu) platform, benchmarked against three other OCR/HTR models ([Czech Slovak Model Print M1](https://www.transkribus.org/models/czech-slovak-print-model-m1), [Text Titan I](https://www.transkribus.org/models/the-text-titan-i-super-model), [Transkribus Print M1](https://www.transkribus.org/models/transkribus-print-multi-language-dutch-german-english-finnish-french-swedish-etc)) on scanned Burgenland Croatian print sources ([Glasilo](https://hkd.at/), [Hrvatske Novine](https://hrvatskenovine.at/), [ZIGH](https://www.zigh.at/)).

## Results overview — Burgenland Croatian Typewritten 2010-2019

Averages across all 12 evaluated pages (3× Glasilo, 6× Hrvatske Novine, 3× ZIGH):

| Metric | Average |
|---|---|
| CER (Character Error Rate) | 1.01% |
| Character Accuracy | 98.62% |
| WER (Word Error Rate) | 0.0381 |
| Word Accuracy | 94.65% |
| Bag of Tokens F-measure | 0.9776 |

By source:

| Source | Pages | Avg. CER | Avg. WER | Avg. Word Accuracy |
|---|---|---|---|---|
| Glasilo | 3 | 1.32% | 0.0449 | 93.80% |
| Hrvatske Novine | 6 | 0.88% | 0.0293 | 96.16% |
| ZIGH | 3 | 0.95% | 0.0492 | 92.48% |

Per-page results are in the `cer_results_Burgenland_Croatian_Typewritten_2010-2019.csv` files described below; the same folders also hold results for the three comparison models.

### Comparison with the other models

Averages across the same 12 pages, per model:

| Model | Avg. CER | Avg. Character Accuracy | Avg. WER | Avg. Word Accuracy | Avg. Bag of Tokens F-measure |
|---|---|---|---|---|---|
| **Burgenland Croatian Typewritten 2010-2019** | **1.01%** | **98.62%** | **0.0381** | **94.65%** | **0.9776** |
| Transkribus Print M1 | 2.03% | 96.85% | 0.0869 | 86.55% | 0.9322 |
| Text Titan I | 3.93% | 93.39% | 0.1628 | 74.33% | 0.8583 |
| Czech Slovak Model Print M1 | 4.67% | 92.55% | 0.2095 | 68.87% | 0.8209 |

The Burgenland Croatian model consistently outperforms the three general-purpose comparison models on this data, which is expected since it was trained specifically for this script and language.

## Folder structure

- **`Glasilo/`** — Per-page CER (Character Error Rate) evaluation results for the *Glasilo*. Each `page N/` subfolder holds one CSV per model tested on that page.
- **`Hrvatske Novine/`** — Per-issue, per-page CER evaluation results for *Hrvatske Novine*. Organized as `DD.MM.YYYY/page N/`, one CSV per model per page.
- **`ZIGH/`** — Per-page CER evaluation results for the *ZIGH*. Each `page N/` subfolder holds one CSV per model tested on that page.
- **`export/`** — Raw Transkribus exports used as the source material for evaluation, one subfolder per document (named by Transkribus document ID), each containing the original PDF, plain-text transcription, and full page/metadata export (`metadata.xml`, `mets.xml`, `page/`).
- **`Final Testing Burgenland Croatian.csv`** — Source document metadata for the three evaluated documents (Transkribus document ID, title, page count, upload date, and view/thumbnail links).

## CSV naming convention

Inside each `page N/` folder, evaluation results are split one file per model:

- `cer_results_Burgenland_Croatian_Typewritten_2010-2019.csv` — the model under evaluation
- `cer_results_Czech_Slovak_Model_Print_M1.csv` — [Czech Slovak Model Print M1](https://www.transkribus.org/models/czech-slovak-print-model-m1)
- `cer_results_Text_Titan_I.csv` — [Text Titan I](https://www.transkribus.org/models/the-text-titan-i-super-model) 
- `cer_results_Transkribus_Print_M1.csv` — [Transkribus Print M1](https://www.transkribus.org/models/transkribus-print-multi-language-dutch-german-english-finnish-french-swedish-etc)

Each CSV reports, per page: CER, Character Accuracy, WER, Word Accuracy, and Bag of Tokens Precision/Recall/F-measure.
