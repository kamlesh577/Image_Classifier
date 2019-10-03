# Image Classifier
## This repository contains keras image classifier that can classify whether the given image is of a dog or cat
 
In our examples we will use two sets of pictures, which we got from Kaggle: 1000 cats and 1000 dogs (although the original dataset had 12,500 cats and 12,500 dogs, we just took the first 1000 images for each class). We also use 400 additional samples from each class as validation data, to evaluate our models.

That is very few examples to learn from, for a classification problem that is far from simple. So this is a challenging machine learning problem, but it is also a realistic one: in a lot of real-world use cases, even small-scale data collection can be extremely expensive or sometimes near-impossible (e.g. in medical imaging). 

## How do computers see?
For a computer, an image is just an array of values. Typically it’s a 3-dimensional (RGB) matrix of pixel values.
For example, a 6x6 RGB abstract image representation would look like this.

 ![1_9TbWVXICJaXxUsCzg1wrDQ](https://user-images.githubusercontent.com/38343027/66099238-bc2d9c80-e5c3-11e9-875a-db1866f5333f.png)

Where each pixel has a specific value of red, green and blue that represents the color of a given pixel.

![1_Q39MdvBKPMkihqLFQoq82A](https://user-images.githubusercontent.com/38343027/66099308-0c0c6380-e5c4-11e9-956a-4b41e44624b5.png)


## Convolutional Neural Networks (CNNs)
CNNs are deep learning models suited for analyzing visual imagery. They are heavily influenced by how we - humans see.CNN processes images using matrixes of weights called filters (features) that detect specific attributes such as vertical edges, horizontal edges, etc. Moreover, as the image progresses through each layer, the filters are able to recognize more complex attributes. Ultimate goal of the CNN is to detect what is going on in the scene.

 ### Convolution
The ultimate purpose of this layer is to receive a feature map. Usually, we start with low number of filters for low-level feature detection. The deeper we go into the CNN, the more filters (usually they are also smaller) we use to detect high-level features.

![Webp net-resizeimage (2)](https://user-images.githubusercontent.com/38343027/66099964-a2da1f80-e5c6-11e9-88c9-d08afdb0bec7.png)

Feature detection is based on ‘scanning’ the input with the filter of a given size and applying matrix computations in order to derive a feature map.

![1_-OM6jQTMNACDX2vAh_lvMQ](https://user-images.githubusercontent.com/38343027/66099717-8e495780-e5c5-11e9-8441-589b5e79e8e4.png)


![Uploading 1_h1S9FFDHmmj5yY_Y3uMcgw.gif…]()


## Activation
Without going into further details, we will use ReLU activation function that returns 0 for every negative value in the input image while it returns the same value for every positive value.
