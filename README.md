# vanilla-gan-tf2

Here you will find the simplest and easy to follow TF 2.0 implementation for Generative Adversarial Network.

I have made it as simple as possible for those who want to understand the main idea behind GAN


### What is GAN ?

![Alt text](images/Yann.png?raw=true "Title")

For short description read this wikipedia [Generative Adversarial Nets](https://en.wikipedia.org/wiki/Generative_adversarial_network) article.

### How the generator outputs images that is identical to distribution of the training examples by sampling from random noise ?

Ok first, Do you have any idea on how to sample from arbitrary and complex probability distribution function ?
There are different techniques that are aimed at generating complex random variables such as inverse transform method, rejection sampling, Metropolis-Hasting algorithm and others.

Let's talk about inverse transform method which is simply to represent a complex random variable X as the result of a function applied to a uniform random variable Z that we know how to generate from (like uniform distribution)

Given that the random variable X is fully defined by its Cumulative Distribution Function (CDF),
Then we can generate random samples from the X using its Inverse Cumulative Distribution Function (ICDF) as shown below

![Alt text](images/IS-method.png?raw=true "Title")

where z is sampled from unifrom distribution (That's easy to sample from) and x is calculated using ICDF of the complex random distribution function X.

### How all of above is related to GAN ?
We want the generator to produce images that have the same underlying distribution of the training examples. But we don't know any thing about this underlying distribution (Let think what if you don't have the ICDF in the above method!) What could we do ?

We can use neural network to represent this transform function that map from simple probability distribution function to a complex and unknow disitibution function using the below algorithm

### Training algorithm

Find below the training algorithm for GAN as introduced in 2014 by Ian J. Goodfellow and co-authors in [Generative Adversarial Nets](https://arxiv.org/abs/1406.2661) paper

![Alt text](images/algorithm.png?raw=true "Title")

### References
- [GAN paper](https://arxiv.org/abs/1406.2661) by Ian J. Goodfellow and co-authors.
### Contact
To ask questions or report issues, please open an issue on the [issues tracker](https://github.com/eng-amrahmed/vanilla-gan-tf2/issues)


