# Neural Network for Fashion MNIST Classification

Hey there! This is a fun little project where I built a neural network to classify grayscale images of clothes from the Fashion MNIST dataset. It's like the classic MNIST but with fashion items instead of digits – think t-shirts, sneakers, bags, and more. The goal was to make a model that's accurate, trains quickly, and handles variations in images without freaking out.

I experimented with a simple fully connected network, then tweaked it to make it deeper and wider, added TensorBoard for tracking progress, and even dove into some ethical stuff like dataset biases. If you're into PyTorch and machine learning basics, this might be a cool starting point to play around with.

## What's Inside?

- **Problem Breakdown**: We're classifying 28x28 grayscale images into 10 categories: T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, and Ankle boot.
- **Goals**:
    - Get the highest accuracy on unseen data.
    - Keep training efficient (especially if you've got a GPU).
    - Make the model tough against things like lighting changes or rotations.
- **Ethical Notes**: Fashion MNIST is mostly Western clothes, so it might not handle global fashion well. There could be biases toward certain styles or genders, which isn't great for real apps like shopping recommendations. I talked about this and even simulated some bias fixes.


## Dataset

We're using Fashion MNIST – 70,000 images split into train (60k) and test (10k), all nicely balanced across classes. I loaded it via PyTorch's torchvision, normalized the pixels, and batched it up for training.

## Project Steps

- **Load Data**:
Load Fashion-MNIST dataset from Torchvision library

- **Simple Model**:
A basic fully connected net with layers: 784 -> 128 -> 64 -> 10. Uses ReLU and Adam optimizer.
- **Training**:
Run for 10 epochs, track loss and accuracy. Example output: Test accuracy around 86-87%.
- **Improvements**:
    - Deeper version: Added more layers, dropped LR to 0.0005 – hit ~88% accuracy.
    - Wider version: More neurons, bigger batches – got to ~89%.
    - TensorBoard logs for comparing runs.
- **Bias Stuff**:
I artificially imbalanced the data to show issues, then talked about fixes like weighted sampling.

Just copy-paste sections into a notebook and run them step by step.

## Results

- Baseline Simple NN: ~86.58% test accuracy after 10 epochs.
- Deeper NN: ~88.54%.
- Wider NN: ~88.62%.
- Per-class accuracies vary – great on trousers (~96%), meh on shirts (~67%) due to similarities.

Check TensorBoard logs in the `runs` folder for graphs of loss and accuracy over epochs.

## Analysis

The models improve with depth and width, but fully connected nets aren't perfect for images – they'd probably do better as CNNs. On biases: The dataset is balanced, which is awesome, but in real life, watch out for underrepresented classes. I simulated imbalance and saw accuracy drop, so techniques like oversampling help.

If you spot bugs or want to tweak it, feel free to fork and mess around! This was a learning exercise, so nothing fancy – just solid basics.


