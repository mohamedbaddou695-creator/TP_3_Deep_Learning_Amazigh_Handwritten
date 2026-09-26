# Tifinagh Handwritten Character Classification Using a NumPy MLP

Authors: [complete]
Affiliation: [complete]

**Working outline — not a completed article. Replace every bracketed instruction after running the experiments.**

## Abstract
[Summarize the objective, dataset actually used, approach, measured test results and main limitation.]

## 1. Introduction
[Explain handwritten Tifinagh recognition, motivation and the objective of implementing forward and backward propagation manually. Cite the dataset.]

## 2. Methods
### Dataset and preprocessing
[Specify the release, actual sample counts and classes. Describe grayscale conversion, 32 × 32 resizing, normalization and flattening.]
### Experimental protocol
[Report stratified 60/20/20 image split, seed, and the absence or presence of writer separation. Explain checkpoint selection using validation loss.]
### Architecture and mathematical formulation
[Describe 1024/64/32/33 layers, ReLU, Softmax, cross-entropy, gradients and SGD updates. Include equations from the assignment and explain symbols.]
### Hyperparameters
[Copy the actual settings from results/config.json. Mention any departures from the baseline and any bonus actually completed.]

## 3. Results
[Insert your measured test accuracy and macro/weighted F1. Insert loss_accuracy_plot.png and confusion_matrix.png, with captions and explanations. Do not use the assignment's example figures as your own results.]

## 4. Discussion
[Interpret confusions and train/validation differences. Discuss image-level splitting, writer generalization, flattening, reproducibility and computational limits. Distinguish measured improvements from proposed future work.]

## 5. Conclusion
[Summarize what your experiment establishes and one realistic future direction.]

## Code availability
Repository: [paste your actual GitHub URL]

## References
[Complete and verify the AMHCD citation and any other sources actually used.]
