# Paramilitary-Uniform-Detection-with-Deep-Learning
Given an Image of a paramilitary belonging to either CRPF, BSF or J&amp;K police, the model detects which category It belongs to.
The model handles edge cases such as different uniforms within each class such as Rapid Action Force(RAF), Regula Combat Camouflage, and regular khaki for CRPF class for instance.

## About the dataset
The dataset is collected from the internet, such as google image, Twitter, dedicated websites, public websites, etc. Each category contains images around 170 images and a total of 500 images. 
![a-crpf-personnel-stands-guard-in-hindpirhi-coronavirus-containment-zone-on-may-13-2020-in](https://github.com/tjorgais/Paramilitary-Uniform-Detection-with-Deep-Learning/assets/42938890/281cf9b1-ae36-4863-9a20-e15358920ffb)
![an-indian-border-security-force-soldier-looks-through-binoculars-during-a-patrol-at-the-india2](https://github.com/tjorgais/Paramilitary-Uniform-Detection-with-Deep-Learning/assets/42938890/36c4b604-4db8-42db-8fb5-d07b65069383)
![inspector-general-of-police-vijay-kumar-during-the-wreath-laying-ceremony-of-police-cop3](https://github.com/tjorgais/Paramilitary-Uniform-Detection-with-Deep-Learning/assets/42938890/02457ed7-89d3-47cf-80a0-ea97128a2190)


# Defining Model
After preprocessing the dataset, such as resizing and other transformations. The model to classify the images is defined.
The model defined is a pre-trained VGG16 model. Although I experimented with different models like Resnet18, and Resnet50, defining the CNN model from scratch but VGG16 was best for this task. The last layer is changed to incorporate the number of classes for this task. The model is fined tuned completely to learn features for this particular task. The loss function used here is cross-entropy loss, and the optimizer is Adam, with a learning rate of 1e-5.

# Model Traning and Testing
The model is trained for 60 epochs. The validation set for the model is to tune the hyperparameter and track the validation loss to avoid overfitting. Here early stopping is employed with a patience parameter of ten epochs to avoid overfitting. The plot for training, validation loss and accuracy is added below. The model is tested on datapoint more than 100 from all three classes. 
![image](https://github.com/tjorgais/Paramilitary-Uniform-Detection-with-Deep-Learning/assets/42938890/3e3f1f7b-6194-4cc7-b23c-b077ff3c3bcf)



## Result
To evaluate the model performance, accuracy, weighted precision, recall and F1 score are computed on the test set. Also, the confusion matrix is plotted for test set.

