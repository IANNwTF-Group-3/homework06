# homework06

Our original model had no problems with the dataset and did not overfit. We could observe this by looking at the test accuracy and the respective losses.

Using the optimization methods, the model now performs worse than before. We tried different ways of applying the methods including many parameters but a combination of everything always leads to such result.

In the end we used:
1. Data augmentation
   
   This modifies the image by applying e.g. Rotation or mirrors the image at one axis. This gives us a variaty of test data to train our model with a even more complex task. (Which is useful, if the model can memorize every given data)
2. Regularizer

   We choose kernel regularizer (L1 and L2) for all convolutional layers to prevent the weights from becoming too large. This can regulate overfitting caused by other optimization techniques.
3. Dropout

   A dropout layer sets some units randomly to zero. Using this, we kind of introduce some noise to the input images as well as the hidden layer activations.
4. Label smoothing

   Label smoothing counter hard labels by using a soft probability distribution for classification instead. This might be beneficial for such a classification task.
5. BatchNormalization

   To avoid too large activations, we use a batch normalization layer in the end. This normalizes the output, in case there are too big or too small values.

Unfortunately, Google Colab limits the use of GPU Accelerators so we could not test more permutation of the methods... We worked through our Google Accounts and are waiting to get our GPUs back...