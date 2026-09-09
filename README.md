# Fish Disease Detection

Automatically detecting diseases in South Asian freshwater fish — one of aquaculture's costliest problems — using convolutional neural networks.

Fish farmers lose huge numbers of stock to disease every year, and spotting a sick fish still mostly comes down to a trained human eye. This project asks: can a neural network look at a photo of a fish and tell whether it's healthy or which of six common diseases it has?

## The approach

Three models were built and compared, each one improving on the last:

| Model | Approach | Test accuracy |
|---|---|---|
| `CNN_Baseline.ipynb` | CNN trained from scratch | ~40% (underfit — an early experiment) |
| `TransferLearning_ImageNet.ipynb` | ImageNet-pretrained backbone, fine-tuned | ~71% |
| `Fishnet_CNN.ipynb` | Tuned CNN: conv layers + max-pooling + dense layers + dropout, Adam optimizer, categorical cross-entropy | **92.5%** |

The final model classifies **7 categories** — healthy fish plus bacterial red disease, aeromoniasis, bacterial gill disease, saprolegniasis (fungal), parasitic diseases, and white tail disease (viral) — with macro-averaged precision, recall, and F1 all at **0.93** across 697 test images.

## What's in this repo

| Folder | Contents |
|---|---|
| `notebooks/` | All three model notebooks, from baseline experiment to final model |
| `poster/` | Research poster (48×36): "Enhancing Disease Detection in South Asian Freshwater Fish Aquaculture Through Convolutional Neural Networks" |
| `docs/` | Project report (PDF) with full results and per-class metrics |
| `data/` | `classification.txt` — the 7 class labels |

### Data note

The training images (1,747 fish photos) are not stored here. The notebooks document the dataset source and expected layout — see `data/classification.txt` for the label mapping.

## Authors

Hayin Tamut, **Musfikur Rahaman**, Dr. Robin Ghosh — Department of Engineering and Computing Sciences, Arkansas Tech University.
