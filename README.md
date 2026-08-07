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

## Detailed per-document performance comparison

Bold values indicate the lowest CER for each evaluated page.

| Source | Pages | Model | CER per page (%) | Processing time per page |
|---|---|---|---|---|
| Hrvatske novine (8 April 2011) | 3 / 4 / 8 | **Burgenland Croatian Typewritten 2010-2019** | **2.25 / 0.75 / 0.50** | **14 s 982 ms / 23 s 600 ms / 19 s 830 ms** |
|  |  | Text Titan I | 4.46 / 4.32 / 4.30 | 45 s 726 ms / 36 s 54 ms / 1 m 11 s 54 ms |
|  |  | Transkribus Print M1 | 2.16 / 2.40 / 2.00 | 12 s 710 ms / 17 s 629 ms / 13 s 351 ms |
|  |  | Czech Slovak Model Print M1 | 3.73 / 5.66 / 3.88 | 19 s 666 ms / 9 s 963 ms / 18 s 695 ms |
| Hrvatske novine (25 October 2013) | 2 / 14 / 18 | **Burgenland Croatian Typewritten 2010-2019** | **0.35 / 0.44 / 0.97** | **21 s 545 ms / 17 s 757 ms / 21 s 398 ms** |
|  |  | Text Titan I | 4.31 / 5.01 / 4.38 | 1 m 6 s 961 ms / 1 m 14 s 370 ms / 56 s 935 ms |
|  |  | Transkribus Print M1 | 1.74 / 2.86 / 2.52 | 13 s 5 ms / 17 s 590 ms / 20 s 539 ms |
|  |  | Czech Slovak Model Print M1 | 4.62 / 5.49 / 5.25 | 16 s 294 ms / 3 s 725 ms / 13 s 304 ms |
| Glasilo (December 2020) | 2 / 3 / 7 | **Burgenland Croatian Typewritten 2010-2019** | **1.46 / 1.18 / 1.47** | **12 s 167 ms / 15 s 345 ms / 19 s 530 ms** |
|  |  | Text Titan I | 4.43 / 4.13 / 3.66 | 48 s 675 ms / 1 m 7 s 747 ms / 34 s 670 ms |
|  |  | Transkribus Print M1 | 3.91 / 2.40 / 2.35 | 12 s 24 ms / 14 s 995 ms / 11 s 126 ms |
|  |  | Czech Slovak Model Print M1 | 5.31 / 4.53 / 4.38 | 14 s 803 ms / 14 s 930 ms / 16 s 178 ms |
| ZIGH document (May 2025) | 1 / 2 / 3 | **Burgenland Croatian Typewritten 2010-2019** | **0.91 / 1.12 / 0.82** | **19 s 756 ms / 19 s 482 ms / 17 s 873 ms** |
|  |  | Text Titan I | 2.13 / 2.98 / 3.07 | 26 s 449 ms / 31 s 237 ms / 29 s 648 ms |
|  |  | Transkribus Print M1 | 0.87 / 0.91 / 1.27 | 11 s 265 ms / 12 s 306 ms / 11 s 928 ms |
|  |  | Czech Slovak Model Print M1 | 3.66 / 3.67 / 5.54 | 12 s 986 ms / 9 s 869 ms / 13 s 235 ms |

## Comparison with Croatian OCR tools

Bold values indicate the lowest CER for each evaluated page.

| Source | Pages | Model/tool | CER per page (%) |
|---|---|---|---|
| Hrvatske novine (8 April 2011) | 3 / 4 / 8 | **Burgenland Croatian Typewritten 2010-2019** | **2.25 / 0.75 / 0.50** |
|  |  | i2OCR | 3.06 / 2.92 / 9.91 |
|  |  | Convertio | 4.25 / 2.31 / 5.86 |
|  |  | Tesseract (HR) | 3.10 / 2.44 / 1.30 |
| Hrvatske novine (25 October 2013) | 2 / 14 / 18 | **Burgenland Croatian Typewritten 2010-2019** | **0.35 / 0.44 / 0.97** |
|  |  | i2OCR | 1.61 / 4.55 / 5.31 |
|  |  | Convertio | 3.03 / 3.26 / 3.03 |
|  |  | Tesseract (HR) | 1.09 / 3.53 / 1.84 |
| Glasilo (December 2020) | 2 / 3 / 7 | **Burgenland Croatian Typewritten 2010-2019** | **1.46 / 1.18 / 1.47** |
|  |  | i2OCR | 14.94 / 0.77 / 1.51 |
|  |  | Convertio | 3.16 / 3.14 / 2.39 |
|  |  | Tesseract (HR) | 2.46 / **0.73** / 4.66 |
| ZIGH document (May 2025) | 1 / 2 / 3 | **Burgenland Croatian Typewritten 2010-2019** | **0.91 / 1.12 / 0.82** |
|  |  | i2OCR | 0.57 / 0.52 / 0.90 |
|  |  | Convertio | 1.39 / 1.34 / 2.21 |
|  |  | Tesseract (HR) | 3.61 / 0.52 / 0.94 |

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
