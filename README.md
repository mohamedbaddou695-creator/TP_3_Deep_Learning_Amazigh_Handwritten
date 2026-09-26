# Tifinagh Handwritten Character Classification with a NumPy MLP

This project implements a multilayer perceptron (MLP) to classify handwritten Tifinagh characters into 33 classes. It was developed as part of a neural networks practical assignment. Forward propagation, backpropagation and parameter updates are implemented manually using NumPy, without a deep learning framework.

The dataset is AMHCD version 1, available at [Amazigh Handwritten Character Database](https://www.kaggle.com/datasets/benaddym/amazigh-handwritten-character-database-amhcd). The recorded experiment loads one copy containing 25,740 images. After preprocessing, 84 repeated inputs and four inputs with conflicting labels are removed, leaving 25,652 images. Images are converted to grayscale, resized to 32 × 32 pixels, normalized to the range [0, 1], and flattened into vectors of 1,024 features.

The data is divided into training, validation and test sets using a stratified 60/20/20 split with a random seed of 42. The resulting sets contain 15,390 training images, 5,131 validation images and 5,131 test images. This is an image-level split and does not guarantee separation between writers.

The network contains an input layer of 1,024 features, two hidden layers with 64 and 32 neurons, and an output layer with 33 neurons. ReLU is used in the hidden layers, while Softmax produces class probabilities at the output. The model has 68,769 trainable parameters and uses categorical cross-entropy as its loss function.

The baseline is trained using mini-batch stochastic gradient descent with a learning rate of 0.01, a batch size of 32 and 100 epochs. Initial weights are sampled from a normal distribution scaled by 0.01. The parameters from the epoch with the lowest validation cross-entropy are restored before final evaluation. The test set is not used to select the checkpoint.

In this execution, the model was trained for 100 epochs, and the checkpoint from epoch 99 was selected based on the lowest validation cross-entropy. It achieved a test accuracy of **86.65%**, a macro F1-score of **0.8666**, a macro precision of **0.8715**, and a macro recall of **0.8666**. The test cross-entropy was **0.4650**, with **685 incorrect predictions out of 5,131 test images**. At the selected checkpoint, training accuracy was **88.16%** and validation accuracy was **87.31%**. Training took approximately **143 seconds** on the machine used for this run. These results describe a single image-level split and do not establish performance on unseen writers.

The learning curves, confusion matrix, character examples and prediction errors are saved in `results/baseline/`. This directory also contains the metrics in `results.json`, per-class metrics, test predictions, split assignments and model weights. These outputs support the analysis of learning behaviour and confusion between character classes.

To run the project, install the dependencies with `python -m pip install -r requirements.txt`, then start Jupyter with `python -m notebook`. Open `Notebook_Tifinagh_A.ipynb` and execute its cells in order. The notebook attempts to download the AMHCD archive if `amhcd.zip` is missing. An existing archive can be used by setting `DATA_FILE` to its location. The loader expects the folder structure of AMHCD version 1.

The results demonstrate the performance of a NumPy MLP on this particular image-level split. They do not establish performance on unseen writers. Flattening the images also means that the model does not explicitly exploit their spatial structure. Future experiments could investigate other initializations, regularization, optimization methods and writer-independent evaluation.

This project was prepared by **Halima Baddou** as part of the Master’s programme in Artificial Intelligence.
