# General LNP CV5 model — strong overall, weak brain-specific

Saved and verified on **July 30, 2026**.

## Classification

This is a valid five-fold Chemprop model and is worth preserving as a **strong
general LNP model**.

It is **not** the presentation model and should **not** be described as a good
brain-specific model. Its overall held-out performance is stronger than the
older presentation result, but its performance on the 92 held-out brain rows is
poor.

## Fresh evaluation results

These metrics were calculated from fresh predictions made with the five saved
checkpoints:

| Evaluation set | Rows | Pearson | Spearman | RMSE |
| --- | ---: | ---: | ---: | ---: |
| All held-out rows | 8,805 | 0.4813 | 0.4260 | 0.8767 |
| Brain-only held-out rows | 92 | -0.1585 | -0.0769 | 1.0716 |

For context, the presentation result across all held-out rows was approximately
Pearson 0.434 and Spearman 0.363.

The saved 7,100-row screening output only weakly matches the presentation
ranking:

| Comparison with presentation screen | Rows | Pearson | Spearman |
| --- | ---: | ---: | ---: |
| Shared screening candidates | 7,100 | 0.1939 | 0.1725 |

## What is preserved here

- `general_lnp_cv5_overall_P0p481_S0p426_brain_weak_2026-07-30_ORIGINAL.zip`
  is a byte-for-byte copy of the supplied recovery archive.
- `checkpoints_and_splits/` contains all five model checkpoints plus the exact
  train, validation, and test splits, added features, weights, metadata, model
  settings, logs, and saved score files.
- `screen_predictions/` contains the 7,100-row screening prediction table.
- `good_presentation_reference.tsv` is the presentation-ranking reference that
  was bundled with the recovery archive.
- `SHA256SUMS.txt` records the identities of the original archive and all five
  checkpoints.

## Critical warning about predictions

The `preds.csv` file inside each `cv_*` folder was written at approximately
19:03 on July 30, 2026, before the new checkpoints were finished at
approximately 19:16–19:39. Those five `preds.csv` files are therefore stale and
must not be used to evaluate these checkpoints.

The fresh 8,805-row prediction table used to calculate Pearson 0.4813,
Spearman 0.4260, and RMSE 0.8767 was produced after this ZIP was created and is
not included in the supplied archive. To recreate those metrics, run prediction
with the five preserved `model.pt` checkpoints and concatenate each fold's
held-out predictions.

The saved screening table is internally consistent: its average prediction is
the mean of its five fold prediction columns.

## Safe usage

Use this model for general LNP prediction experiments when the mixed-data
overall performance is the relevant criterion. Do not use its brain-only
metrics as evidence that it can rank brain-delivery lipids.

Never overwrite this directory or the original ZIP. Save future runs under a
new name and compare their checksums and metrics with this record.

