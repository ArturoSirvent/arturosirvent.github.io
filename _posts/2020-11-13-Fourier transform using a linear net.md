---
title: "Fourier Transform performed in a Neural Network"
date: 13/11/2020
tags: [NN, fourier, deep learning,linear combination,filters]
excerpt: "How it is the Fourier transform implemented into a NN."
mathjax: "true"
---


**First we should get make the training set:**

This can be done easily performing the (discrete) fast fourier transform to a set data randomly distributed.
Realize that the discrete fourier transformation is nothing but a linear combination with a very concrete coefficients.

$$A_k =  \sum_{m=0}^{n-1} a_m \exp\left\{-2\pi i{mk \over n}\right\} \qquad k = 0,\ldots,n-1.$$

Where $$A_k$$ (vector elements in the momentum space) is made of lineary combining $$a_m$$ weighted with $$\exp\left\{-2\pi i{mk \over n}\right\}$$ , those coefficients can be obtained even before knowing the $$a_m$$ data. That means it can be seen as a vector transformation, done by a known matrix $$M$$, applied to a vector $$a$$ which finally gives the desired vector $$A$$.

$$ A = M a$$

Also we should know that a neural network with no activation function (non-linear functions) can be seen as a linear combination of the inputs.
*(Even if the NN has more than one layer, the whole proccess can be summed up to a one layer NN without activation functions.)*

![][`https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.researchgate.net%2Ffigure%2FOne-layer-neural-network-and-nomenclature-employed_fig1_221079407&psig=AOvVaw2NicU6jefsYqtWul3UfCYE&ust=1605444212708000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCKifoLeIgu0CFQAAAAAdAAAAABAD `]

That is why we use just one fully connected layer and no activation function is needed.

**The implementation is as follows:**





All this post is my own replication of the results shown in <a href="https://gist.github.com/endolith/98863221204541bf017b6cae71cb0a89">here</a> :
<script src="https://gist.github.com/endolith/98863221204541bf017b6cae71cb0a89.js"></script>
