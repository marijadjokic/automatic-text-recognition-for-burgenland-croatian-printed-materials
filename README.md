# Evaluation Files

Repository: https://github.com/marijadjokic/automatic-text-recognition-for-burgenland-croatian-printed-materials

This folder contains the evaluation results of the model **["Burgenland Croatian Typewritten 2010-2019"](https://www.transkribus.org/models/burgenland-croatian-typewritten-2010-2019)** available on the [Transkribus](https://transkribus.eu) platform, benchmarked against three other OCR/HTR models ([Czech Slovak Model Print M1](https://www.transkribus.org/models/czech-slovak-print-model-m1), [Text Titan I](https://www.transkribus.org/models/the-text-titan-i-super-model), [Transkribus Print M1](https://www.transkribus.org/models/transkribus-print-multi-language-dutch-german-english-finnish-french-swedish-etc)) on scanned Burgenland Croatian print sources ([Glasilo](https://hkd.at/), [Hrvatske Novine](https://hrvatskenovine.at/), [ZIGH](https://www.zigh.at/)).

## Folder structure

- **`Glasilo/`** — Per-page CER (Character Error Rate) evaluation results for the *Glasilo*. Each `page N/` subfolder holds one CSV per model tested on that page.
- **`Hrvatske Novine/`** — Per-issue, per-page CER evaluation results for *Hrvatske Novine*. Organized as `DD.MM.YYYY/page N/`, one CSV per model per page.
- **`ZIGH/`** — Per-page CER evaluation results for the *ZIGH*. Each `page N/` subfolder holds one CSV per model tested on that page.
- **`export/`** — Raw Transkribus exports used as the source material for evaluation, one subfolder per document (named by Transkribus document ID), each containing the original PDF, plain-text transcription, and full page/metadata export (`metadata.xml`, `mets.xml`, `page/`).
- **`Final Testing Burgenland Croatian.csv`** — Transkribus document/collection metadata for all documents included in this evaluation:

  | docId | title | pages | uploaded |
  |---|---|---|---|
  | 12715615 | Glasilo | 3 | 2025-12-05 |
  | 13610592 | Images for publication | 4 | 2026-01-12 |
  | 13771439 | ZIGH | 3 | 2026-01-20 |
  | 13824279 | Hrvatske novine | 6 | 2026-01-22 |

## CSV naming convention

Inside each `page N/` folder, evaluation results are split one file per model:

- `cer_results_Burgenland_Croatian_Typewritten_2010-2019.csv` — the model under evaluation
- `cer_results_Czech_Slovak_Model_Print_M1.csv` — [Czech Slovak Model Print M1](https://www.transkribus.org/models/czech-slovak-print-model-m1)
- `cer_results_Text_Titan_I.csv` — [Text Titan I](https://www.transkribus.org/models/the-text-titan-i-super-model) 
- `cer_results_Transkribus_Print_M1.csv` — [Transkribus Print M1](https://www.transkribus.org/models/transkribus-print-multi-language-dutch-german-english-finnish-french-swedish-etc)

Each CSV reports, per page: CER, Character Accuracy, WER, Word Accuracy, and Bag of Tokens Precision/Recall/F-measure.
