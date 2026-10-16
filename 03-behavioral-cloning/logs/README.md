# Logs

Training logs written by `model.py`. Part of [03 - Behavioral Cloning](../README.md).

| File | Contents |
|---|---|
| `history.csv` | Per-epoch `loss` and `val_loss` (mean squared error) for epochs 0 to 16, written by the Keras `CSVLogger`. |
| `model.json` | Keras 1.1.2 architecture description written by `model.py`; identical to `../pretrained/model.json`. `visualize_activations.py` reads this file. |

The training loss is measured on augmented, dropout-regularised batches and the validation loss on un-augmented ones, so the two columns are not directly comparable.
