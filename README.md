# Object-identification-using-CNN-Conv2D-
CNN implementation using keras on simple dataset of 3000 images of cats, dogs, and pandas 

Data Description:
This dataset consists of 3000 images of cats, dogs, and pandas. Each class has a 1000 images and each image is labelled according to the class it belongs.

Number of Samples	Animal	Label <br>
1000 samples	cat	1 <br>
1000 samples	dog	2 <br>
1000 samples	panda	3  <br>

![image](https://user-images.githubusercontent.com/49444353/125944466-98714e26-e9be-4f60-8285-732f61dc0255.png)


The notebook consists of __3 main parts__:
- __Data preparation__: 
    - Even if the data is already quite clean as mentioned before, it still needs some preparation and pre-processing in order to be in appropriate format for performing CNN. It includes
        - Data seperation
        - Reshaping
        - Visualization<br><br>
- __CNN__: 
    - After NN is defined, 
        - The Convolutional step gets added up, 
        - NN parameters initialized and 
        - The model is trained.<br><br>
- __Evaluation__: 
    - Once model is trained, 
        - Evaluate the model performance by 
        - Seeing the progress of the loss and
        - Extract some conclusions.


## Model Architecture


- __Conv2D__<br><br>

    - __filters__: 
        - Usually on the first convolutional layers there are __less filters, and more deeper down the CNN__. 
        - A __power of 2__ is set, and in this case 16 offered poorer performance big CNN was not required for digit recognition.<br><br>

    - __kernel_size__: 
        - The filter size, usually __(3,3) or (5,5)__ is set. 
        - Ii is advised setting one, building the architecture and changing it to __see if it affects the performance__ though it usually doesn't.<br><br>

    - __padding__: Two options

        - _valid padding_: __No__ padding, the image __shrinks__ after convolution.
        - _same padding_ : Padding of __2__, the image __doesn't shrink__ after convolution.<br><br>
    - __activation__:
        - ReLU is represented mathematically by __max(0,X)__ and offers __good performance in CNNs__.<br><br>

- __MaxPool2D__: <br><br>
    - The goal is to __reduce variance/overfitting__ and __reduce computational complexity__ since it makes the image smaller. two pooling options

        - MaxPool2D: Extracts the most important features like __edges__
        - AvgPool2D: Extracts __smooth features__<br><br>

__Conclusion__ is that for binarized images, with noticeable edge differences, __MaxPool performs better__.<br><br>

- __Dropout__:<br><br>

     - It's a useful tool to __reduce overfitting__. 
     - The net becomes __less sensitive__ to the specific weights of __neurons__ and is more capable of better generalization and __less likely to overfit__ to the train data. 
     - The __optimal dropout value in Conv layers is 0.2__, and if you want to implement it in the __dense layers, its optimal value is 0.5__.

[Jupyter Notebook](./Object_identification_using_CNN.ipynb)
