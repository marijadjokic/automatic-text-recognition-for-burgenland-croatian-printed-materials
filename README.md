# Burgenland Croatian - Evaluation Results

This repository contains the evaluation results of the model **["Burgenland Croatian Typewritten 2010-2019"](https://www.transkribus.org/models/burgenland-croatian-typewritten-2010-2019)** available on the [Transkribus](https://transkribus.eu) platform, benchmarked against three other OCR/HTR models ([Czech Slovak Model Print M1](https://www.transkribus.org/models/czech-slovak-print-model-m1), [Text Titan I](https://www.transkribus.org/models/the-text-titan-i-super-model), [Transkribus Print M1](https://www.transkribus.org/models/transkribus-print-multi-language-dutch-german-english-finnish-french-swedish-etc)) and three general-purpose OCR tools ([Tesseract](https://github.com/tesseract-ocr/tesseract), [Convertio](https://convertio.co/), [i2OCR](https://www.i2ocr.com/)) on scanned Burgenland Croatian print sources ([Glasilo](https://hkd.at/), [Hrvatske Novine](https://hrvatskenovine.at/), [ZIGH](https://www.zigh.at/)).

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

Per-page results are in the `cer_results_Burgenland_Croatian_Typewritten_2010-2019.csv` files, one inside each `page N/` subfolder listed in [Folder structure](#folder-structure) (e.g. `Glasilo/page 2/cer_results_Burgenland_Croatian_Typewritten_2010-2019.csv`); see [CSV naming convention](#csv-naming-convention) for the full file list. The same `page N/` folders also hold results for the three comparison models and three comparison tools.

### Comparison with the other models and tools

Averages across the same 12 pages, per model/tool:

| Model/Tool | Avg. CER | Avg. Character Accuracy | Avg. WER | Avg. Word Accuracy | Avg. Bag of Tokens F-measure |
|---|---|---|---|---|---|
| **Burgenland Croatian Typewritten 2010-2019** | **1.01%** | **98.62%** | **0.0381** | **94.65%** | **0.9776** |
| Transkribus Print M1 | 2.03% | 96.85% | 0.0869 | 86.55% | 0.9322 |
| Tesseract | 2.19% | 97.81% | 0.0631 | 93.69% | 0.9467 |
| Convertio | 2.95% | 97.05% | 0.0667 | 93.33% | 0.9398 |
| i2OCR | 3.88% | 96.12% | 0.0798 | 92.02% | 0.9420 |
| Text Titan I | 3.93% | 93.39% | 0.1628 | 74.33% | 0.8583 |
| Czech Slovak Model Print M1 | 4.67% | 92.55% | 0.2095 | 68.87% | 0.8209 |

The Burgenland Croatian model consistently outperforms the three other Transkribus models and the three general-purpose OCR tools on this data, which is expected since it was trained specifically for this script and language.

## Folder structure

- **`Glasilo/`** — Per-page CER (Character Error Rate) evaluation results for the *Glasilo*. Each `page N/` subfolder holds one CSV per model/tool tested on that page.
- **`Hrvatske Novine/`** — Per-issue, per-page CER evaluation results for *Hrvatske Novine*. Organized as `DD.MM.YYYY/page N/`, one CSV per model/tool per page.
- **`ZIGH/`** — Per-page CER evaluation results for the *ZIGH*. Each `page N/` subfolder holds one CSV per model/tool tested on that page.
- **`export/`** — Raw Transkribus exports used as the source material for evaluation, one subfolder per document (named by Transkribus document ID), each containing the original PDF, plain-text transcription, and full page/metadata export (`metadata.xml`, `mets.xml`, `page/`).

## CSV naming convention

Inside each `page N/` folder, evaluation results are split one file per model/tool:

Transkribus models:
- `cer_results_Burgenland_Croatian_Typewritten_2010-2019.csv` — the model under evaluation
- `cer_results_Czech_Slovak_Model_Print_M1.csv` — [Czech Slovak Model Print M1](https://www.transkribus.org/models/czech-slovak-print-model-m1)
- `cer_results_Text_Titan_I.csv` — [Text Titan I](https://www.transkribus.org/models/the-text-titan-i-super-model) 
- `cer_results_Transkribus_Print_M1.csv` — [Transkribus Print M1](https://www.transkribus.org/models/transkribus-print-multi-language-dutch-german-english-finnish-french-swedish-etc)

General-purpose OCR tools:
- `cer_results_Tesseract.csv` — [Tesseract](https://github.com/tesseract-ocr/tesseract)
- `cer_results_convertio.csv` — [Convertio](https://convertio.co/)
- `cer_results_i2OCR.csv` — [i2OCR](https://www.i2ocr.com/)

Each CSV reports, per page: CER, Character Accuracy, WER, Word Accuracy, and Bag of Tokens Precision/Recall/F-measure.
