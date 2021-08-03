# DigitAutoencoder
The second task for the summer Computer vision internship.

The requirment is to build the autoencoder that can make from visibly noised digit image (using MNIST dataset) the readable one.

So, the first step was to make the noisy digit images and create the dataset that could be used for training the Autoencoder. For that purposes I have added to the each scaled image the noise (random value from 0 to 0.4 for each pixel in the original picture). The example of noised digit and it's clear version:

![image](https://user-images.githubusercontent.com/31920760/128072333-7462d551-051f-4db0-976d-d11090deaa64.png)

After that I trained the model that consist of two parts - Encoder and Decoder. Encoder with convolutions reduce the image from the shape (28, 28, 1) to (7, 7, 32) and the Decoder transforms it back.
Training and validation loss after 100 epochs:

![image](https://user-images.githubusercontent.com/31920760/128072844-f1e8d88d-8454-4298-b307-49ca8636ad7f.png)

To evaluate visually the results the sample was randomly picked across images from test set:

![image](https://user-images.githubusercontent.com/31920760/128073021-995aeebc-543f-46b7-be5b-f1833a8753bd.png)

Also, to evaluate model a simple CNN was trained on the MNIST dataset for 10 epochs and then was fed by denoised test dataset. The result is pretty impressive: on the vanilla MNIST dataset the accuracy was 98.54%, on the noised - 38.82% and after denoising by Autoencoder result was 98.33% that is almost the same as with the clean data. That means the shown model works well for removing chosen level of noise (40%).
