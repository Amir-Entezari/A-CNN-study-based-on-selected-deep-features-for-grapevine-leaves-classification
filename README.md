# data-mining-project
## Data Set
The dataset that is considered in this project is about to recognition of the types of grape leaves.In addition to the fruit of the grape tree, the leaves of the grape tree can also be used and based on its type, its price and use are determined. It is not possible to separate these leaves manually on a large scale.Therefore, we try to do the sorting of leaves automatically with the data we have.
### Step 1:
In this step we are going to split the data into training and test data with a ratio of 80 to 20.
For this purpose, we load the data first. We have a zip file that must first be downloaded and then extracted. Since the project is going to be placed in google colab, we save the data in a temporary folder.
![image2](https://user-images.githubusercontent.com/80061534/183645809-ef76e89e-2620-4943-9db2-e4316eac7d69.png)
Now we want to split the data randomly in the ratio of 80 to 20. Therefore, first we shuffle the data and then copy 80 of them to the train folder and the other 20 to test.(We do this for each class)
![image1](https://user-images.githubusercontent.com/80061534/183712904-c95f05bc-eee0-4105-8635-9fa833ba71e5.png)
### Step 2:
Now we want to increase the number of training images using data augmentation.Therefore, using the relevant libraries, we first rotate, flip, zoom, etc. the data; Because it helps to learn more of the model and the model does not depend on the angle of the images. But we note that we do not change the color of the data because the colors of two leaves from two different classes may be similar and cause the model to learn incorrectly.
We also note that augmentation is not part of the test data.
![image3](https://user-images.githubusercontent.com/80061534/183714149-32e3d729-5eb7-44e0-8a67-68c6f994e238.png)
### Step 3:
In this step, we want to classification the data using different CNN neural network architectures (like keras).
Therefore, first we build the model and then we give it training and valid data (which are from training data) so that learning can be done.
![image4](https://user-images.githubusercontent.com/80061534/183720475-55b55a32-bf5b-4327-878f-f0703500f66b.png)
In the above model, CNN is built with three layers, the activation of the first three layers is relu and the activation of the last layer is sigmoid.
As it can be seen in the results, the results are the same with epoch 15, and the accuracy has gone up to 98%!:

![image6](https://user-images.githubusercontent.com/80061534/183727895-60233922-a87e-41c5-b1d5-2d1d7ebc5588.png) ![image5](https://user-images.githubusercontent.com/80061534/183727874-0f254780-302b-4cb1-b14e-822b6e7d64d3.png)

The confusion matrix is also as follows:
![image7](https://user-images.githubusercontent.com/80061534/183728444-7627daf8-4fdb-4fee-933a-dd87ebacd487.png)

### Step 4:
In this step let's use pretrained models available on the Internet and packages: a)VGG16 b)Inception
#### VGG16: 
We run the model on ecpoch=25, according to the plot, the accuracy of the training data goes up to 70 and the test data up to 50, which according to the F1 score, the final accuracy is equal to 52%:
![image9](https://user-images.githubusercontent.com/80061534/183730399-f0d5b165-3988-4bd4-beac-d991a96c4649.png)
![image8](https://user-images.githubusercontent.com/80061534/183730430-69ce4e79-1828-435f-9465-fc49ba046f13.png)

#### Inception:
We run the model with epoch = 25 and observe that its accuracy is good and in some cases it goes up to 70%:
![image10](https://user-images.githubusercontent.com/80061534/183732198-9b519d6e-ba3e-4d6e-a9c9-5d6292a96b46.png)

The red line corresponds to val_accuracy and the blue one corresponds to accuracy.
Its confusion matrix is as follows that its accuracy is not good in most cases.
![image11](https://user-images.githubusercontent.com/80061534/183732875-27ef6414-d797-4950-9bfc-684fce851694.png)


