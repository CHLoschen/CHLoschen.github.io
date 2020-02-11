# Super-Resolution via Deep Learning

Obviously there is some hype concerning deep learning and its sometimes difficult to tell whether this hype is justified or not. Therefore it is sensible to make your own picture about the potential of deep learning. Here are some fascinating results from the [fastai course](https://course.fast.ai/) "Practical Deep Learning for Coders, v3". In [lesson 7](https://course.fast.ai/videos/?lesson=7) of the 2019 course one of the topics was about so-called "superresolution", i.e. to improve(!) the resolution of low-res images with deep learning.

![](/images/lowres.png "original, low res image")
![](/images/predicted.png "generated image")

First of all, the improvement in resolution is quite astonishing - all the details of the cat that have been introduced by the neural net. But also have take a look at the texture of the tree, which was made furry-ish by the neural network... somewhat scary for sure. But it also demonstrates nicely that the missing information in those images cannot be regenerated and that this is a somewhat artistic process. 

![](/images/lowres2.png "original, low res image")
![](/images/predicted2.png "generated image")

Those results have been obtained with the [fastai](https://docs.fast.ai/) python library using a [unet](https://arxiv.org/abs/1505.04597) type structure with a pre-trained [resnet](https://arxiv.org/abs/1512.03385) inside and with a special loss function such as [perceptual loss](http://svl.stanford.edu/assets/papers/JohnsonECCV16.pdf) in order to reproduce the key features of the images. As a matter of fact, for this particular image no generative adversarial network [(GAN)](https://en.wikipedia.org/wiki/Generative_adversarial_network) was used. The images had been converted from high to low resolution priorily and were trained in order to reproduce the high resolution again. The image from above is from the [oxford pet dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/) and of course taken from the validation set (Siamese_55.jpg).
For more information about this and other related fascinating projects by the fastai developers have a look at e.g.[Decrappification, DeOldification, and Super Resolution](https://www.fast.ai/2019/05/03/decrappify/).
