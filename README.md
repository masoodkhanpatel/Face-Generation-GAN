# Face-Generation-GAN

In this project, we have used [generative adversarial network](https://arxiv.org/abs/1406.2661) to generate new images of faces.
We have defined and trained a DCGAN on a dataset of faces.


We have used the [CelebFaces Attributes Dataset (CelebA)](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) to train the adversarial networks. The CelebA dataset contains over 200,000 celebrity images with annotations. 

<img src='assets/processed_face_data.png'>

---

## Improvements that can be made

- The generated samples are decent enough to pass off as human faces.
- Due to dataset containing celebrity images from various countries i. e. belonging to various ethnicities, I can see in the generated samples, that some of them look like multi-ethnic faces. We can diversify the dataset more by balancing the ethnic factor(adding more images of less represented ethnicities)
- Obviously we can use a larger input size greater than 32, as we see the generated images are pixeleted. Larger models also give better result(more features).
- A larger discriminator model could be helpful.
- The data can preproccessed more along with data augmentation to train the model with more data, as data is kind of fuel for the neural networks.
- Soumith Chintala, gives several tips and tricks for improving GANs [here](https://github.com/soumith/ganhacks), like Label Smoothing etc.
- 'As models are trained longer they sometimes collapse a subset of filters to a single oscillating mode.' - [Alex Radford, Luke Metz, Soumith Chintala](https://arxiv.org/pdf/1511.06434.pdf)
- Using hybrid models, such as [LSGAN](https://arxiv.org/pdf/1611.04076.pdf) or [RFGAN](https://arxiv.org/pdf/1801.09195.pdf) or [WGAN](https://arxiv.org/pdf/1701.07875.pdf).
- The batch size used is a bit too large. Try values like 16 to 32 for better results because, if you choose a batch size too small then the gradients will become more unstable and would need to reduce the learning rate. So batch size and learning rate are linked. Also if one use a batch size too big then the gradients will become less noisy but it will take longer to converge.
- Implement dropouts with low drop_prob in discriminator as mentioned [here](https://github.com/tensorflow/magenta/blob/master/magenta/reviews/GAN.md#disadvantages).
- Similar to implementing dropouts in D, use dropout after each deconv layer except the last.
- The beta1 is a bit too high. Values like 0.1 to 0.3 have shown to get best results.
- The current learning rate is okay. The DCGAN with this architectural structure remains stable with lr between 0.0002 and 0.001.

---

## More resources

Here're a few more resources to learn more:

- [DCGAN Tutorial from PyTorch](https://pytorch.org/tutorials/beginner/dcgan_faces_tutorial.html)
- How to Train a GAN: https://github.com/soumith/ganhacks
- Stability of GANs: http://www.araya.org/archives/1183
- MNIST GAN with Keras: https://medium.com/towards-data-science/gan-by-example-using-keras-on-tensorflow-backend-1a6d515a60d0
- https://blog.openai.com/generative-models/
- https://medium.com/@ageitgey/abusing-generative-adversarial-networks-to-make-8-bit-pixel-art-e45d9b96cee7
- [Unit Testing Tutorial](https://cgoldberg.github.io/python-unittest-tutorial/])

