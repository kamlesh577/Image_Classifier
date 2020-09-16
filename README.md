# Image Classifier
## This repository contains keras image classifier that can classify whether the given image is of a dog or cat
 
In our examples we will use two sets of pictures, which we got from Kaggle: 1000 cats and 1000 dogs images (although the original dataset had 12,500 cats and 12,500 dogs, we just took the first 1000 images for each class). We also use 400 additional samples from each class as validation data, to evaluate our models.

That is very few examples to learn from, for a classification problem that is far from simple. So this is a challenging machine learning problem, but it is also a realistic one: in a lot of real-world use cases, even small-scale data collection can be extremely expensive or sometimes near-impossible (e.g. in medical imaging). 

## How do computers see?
For a computer, an image is just an array of values. Typically it’s a 3-dimensional (RGB) matrix of pixel values.
For example, a 6x6 RGB abstract image representation would look like this.

 ![1_9TbWVXICJaXxUsCzg1wrDQ](https://user-images.githubusercontent.com/38343027/66099238-bc2d9c80-e5c3-11e9-875a-db1866f5333f.png)

Where each pixel has a specific value of red, green and blue that represents the color of a given pixel

![Webp net-resizeimage (3)](https://user-images.githubusercontent.com/38343027/66100677-81c6fe00-e5c9-11e9-8fc4-c23cbd4b0242.png)


## Convolutional Neural Networks (CNNs)
CNNs are deep learning models suited for analyzing visual imagery. They are heavily influenced by how we - humans see.CNN processes images using matrixes of weights called filters (features) that detect specific attributes such as vertical edges, horizontal edges, etc. Moreover, as the image progresses through each layer, the filters are able to recognize more complex attributes. Ultimate goal of the CNN is to detect what is going on in the scene.

 ### Convolution
The ultimate purpose of this layer is to receive a feature map. Usually, we start with low number of filters for low-level feature detection. The deeper we go into the CNN, the more filters (usually they are also smaller) we use to detect high-level features.

![Webp net-resizeimage (2)](https://user-images.githubusercontent.com/38343027/66099964-a2da1f80-e5c6-11e9-88c9-d08afdb0bec7.png)

Feature detection is based on ‘scanning’ the input with the filter of a given size and applying matrix computations in order to derive a feature map.

![1_-OM6jQTMNACDX2vAh_lvMQ](https://user-images.githubusercontent.com/38343027/66099717-8e495780-e5c5-11e9-8441-589b5e79e8e4.png)


![1_h1S9FFDHmmj5yY_Y3uMcgw](https://user-images.githubusercontent.com/38343027/66100494-cf8f3680-e5c8-11e9-81b9-4aecb5961b7e.gif)


## Activation
Without going into further details, we will use ReLU activation function that returns 0 for every negative value in the input image while it returns the same value for every positive value.

![1_LaS6Smyz0rcxExHNOs7dfw](https://user-images.githubusercontent.com/38343027/66100623-4c221500-e5c9-11e9-95ae-05df5ec32ae7.jpeg)

Shape remains unchanged, it’s still [32x32x12]

## Pooling
The goal of this layer is to provide spatial variance, which simply means that the system will be capable of recognizing an object as an object even when its appearance varies in some way.
Pooling layer will perform a downsampling operation along the spatial dimensions (width, height), resulting in output such as [16x16x12] for pooling_size=(2, 2).

![1_EjHD2jDX1-OZrnulk5WcTA](https://user-images.githubusercontent.com/38343027/66100753-ca7eb700-e5c9-11e9-9cd0-71f6473f8f33.gif)

## Fully Connected Layer
In a fully connected layer, we flatten the output of the last convolution layer and connect every node of the current layer with the other node of the next layer. Neurons in a fully connected layer have full connections to all activations in the previous layer, as seen in regular Neural Networks and work in a similar way.
The last layer of our CNN will compute the class probability scores, resulting in a volume of size [1x1xNUMBER_OF_CLASSES].

![1_qsbsCVyu376kqdnNcdxmmw](https://user-images.githubusercontent.com/38343027/66100814-0285fa00-e5ca-11e9-8254-bdf8598372f0.png)

## Image classifier using Keras

https://github.com/kamlesh577/Image_Classifier/blob/master/classifier.ipynb
