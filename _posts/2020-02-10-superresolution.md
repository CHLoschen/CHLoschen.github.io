# Super-Resolution via Deep Learning (with fastai)

Obviously there is a big hype concerning deep learning and its sometimes difficult to tell whether this hype is justified or not. In order to find out what is really going on it is advisable to make one's own picture about the potential of deep learning.

For that reason I recommend to study the [fastai](https://course.fast.ai/) lectures on deep-learning given by Jeremy Howard. 
Here are some fascinating results from this course "Practical Deep Learning for Coders, v3". 
In [lesson 7](https://course.fast.ai/videos/?lesson=7) of the 2019 course one of the topics was about so-called "superresolution", i.e. to improve(!) the resolution of low-res images with deep learning. The pictures below are obtained with the jupyter-notebook introduced in this course. Images of low resolution were fed into the neural net and it produced images with high resolution:


![](/images/lowres.png "original, low res image")
![](/images/predicted.png "image improved via neural net")

First of all, the improvement in resolution is quite astonishing - please note all the details on the photograph that have been introduced by the neural net. Of course, the training algorithm has not seen this very picture before.

But also have a look at the texture of the tree, which was made kind of *furry-ish* by the neural network... it gives the tree some kind a animal-like look, somewhat scary for sure. Obviously, the algorithm was not able to distinguish between the tree and a cat body. 

Despite the amazing improvement in resolution that is seen here and also on the image below, this also demonstrates nicely that the missing information in  images cannot be regenerated and that super-resolution is a somewhat artistic process. And it will never be possible to identify a suspect or to read a car plate on a low res surveilance camera as it is done in so many Hollywood movies... such a generative neural net would "fantasize" some random suspect face or some arbitrary letters and numbers which would not correlate with the truth.
Similarly, in the image below, the high resolution result is impressive but the prediction shows some problems separating the carpet from the cat body, they somewhat appear in plane and the perspective somewhow feels wrong. It will be interesting to see if and how such artifacts and subtle details will be overcome in the future.

![](/images/low_res2.png "original, low res image")
![](/images/predicted2.png "image improved via neural net")

Concerning the technical details, those results have been obtained with the [fastai](https://docs.fast.ai/) python library using a [unet](https://arxiv.org/abs/1505.04597) type structure with a pre-trained [resnet](https://arxiv.org/abs/1512.03385) inside and with a special loss function such as [perceptual loss](http://svl.stanford.edu/assets/papers/JohnsonECCV16.pdf) in order to reproduce the key features of the images. 
As a matter of fact, for this particular image no generative adversarial network [(GAN)](https://en.wikipedia.org/wiki/Generative_adversarial_network) was used, which had been de-facto state-of-the-art for such kind of generative models before.

The images had been converted from high to low resolution priorily and were trained in order to reproduce the high resolution again. The image from above is from the [oxford pet dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/) and of course taken from the validation set (Siamese_55.jpg).

All in all, I believe this is a great and instructive example, as it simultaneously highlights the limits and and the potentials of deep learning.

For more information about this and other related fascinating projects by the fastai developers have a look at e.g.[Decrappification, DeOldification, and Super Resolution](https://www.fast.ai/2019/05/03/decrappify/).


