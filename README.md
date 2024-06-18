# Trojan-Horse-detection
Below I have provided a walk through of what is going on in the code 

**Welcome**

This is the notebook I created from the trojan horse Kaggle dataset, here is the link:

https://www.kaggle.com/datasets/subhajournal/trojan-detection

The first two blocks of code are directly from the Kaggle webiste and are vital to importing the data correctly and efficently. In each section, there are comments explaining lines of the code and introductions to each code block explaining the processes below

**Introduction to Trojan Horse Malware**

A trojan horse attack is a malware that disgusies itself as legitmate code or software. Once the malware has infected the device the attackers are able to perform any tasks an authorized user could get. The most common way these attacks are carried out is through social engieering tatics such as phising and spoofing.

You could hear people sometimes refer to a trojan horse as a virus, but however this would be incorrect. A computer virus, much like a health virus, is able to duplicate itself or self-execute. A malware is something that is there to disrupt, disturb, or destroy some things on a computer. This is why trojan horse attacks are known malware. Trojan horse attacks get access to the computers to destroy, move, exploit, or disrupt files, also some attakcs will download viable information to later on sell.

Due to their discreition, trojan horse attacks are one of the most common known malwares. As said before, trojan malware commonly uses social engineering tactics to infect the users devices. These types of attacks are easily taken because of their multiple and easy ways of infecting devices. For example, not reading the fine print when downloading software, opening pirated media, and accepting or allowing a pop-up notifaction.

Below is a multi-layered perceptron that takes in a dataset of trojan horse attacks and then makes predictions about when a trojan horse attack may occur.

**Loading the data**

The next block of code (4), is the process of downloading, cleaning, and loading the data for testing and training. Our target labels are going to be "Trojan" and "Benign", these are referring to the tops of attacks which could occur, then we convert them into bianry 1s and 0s for the model to process. Next, we do the same process for the categorical features. These features are the attributes of the data which contribute to the target labels outcome.

Next, we split the data into batch sizes of 32 for the model to take in during the training and testing process. Splitting the data into chunks prevents problems to occur with overfitting and having ram issues when reading the data.

**Model Building**

The choosen model for this dataset was a multi-layered perceptron (MLP). MLPs are deep learning algorithms that closely resemble the architecture of the brain neural networks. Each layer has a set of neurons, which are fully-connected to the layer before it. These connections hold weights which are important in the calculations of activations for the neurons. However, the neurons are all independent of each other, unlike recurrent neural networks where the neurons all rely on other inputs and outputs.

In the init function, we are declaring the 5 layers we will use in this model. The first one being the input layer, the next three are our hidden layers, and the last layer will be the output. In the next function, forward propagation is occuring where the information is being feed forward. The hidden layers process the data it is inputted, applies the activiation function, and then passes it to the next layer. We then declare the loss function and the optimizer to be used in the training and testing process.

**Training the Model**

In the following code block, we are taking our model through the training and evaluation process. There are 20 batches of training taken and we apply our optimizers, loss, and use gradient descent. Again, if you aren't familiar with these terms I highly suggest you to look into the PyTorch documentations. Calling model.train() means we are putting our model into the trianing mode and then model.eval() means we are putting our model into the evaluation mode.

**Showing the Results**

As you can see, we are comparing the training loss, validation loss, training accuracy, and validation accuracy. Training accuracy is the percentage of correct predictions made by the model on the training dataset. Validation accuracy is the percentage of correct predictions made by the model on the validation dataset.Training loss is a measure of how well the model's predictions match the true labels on the training dataset. It is typically computed using a loss function (e.g., cross-entropy loss for classification, mean squared error for regression). alidation loss is a measure of how well the model's predictions match the true labels on the validation dataset. We are graphing these encoutners to show the differences and the encounters.

Real-World Application
It is useful to have the ability to predict these attacks, but how should someone go forward with this information? To prevent future malware attacks, most articles online will tell you to utilize spam applications, only accessing certain urls, and informing yourself and employees of the dangers of phising and spoofing tactics. Once you could detect a malware attack happening on your device, the most important step is contacting your technical support, if a business enviroment, or talk to a technical professional.

**Links for reading**

Basics on Trojan Horse attacks

https://www.crowdstrike.com/cybersecurity-101/malware/trojans/
https://www.webroot.com/us/en/resources/tips-articles/what-is-trojan-virus
PyTorch Documentation

https://pytorch.org/tutorials/beginner/basics/intro.html
Written documentation on a basic introduction to deep learning and MLPS

https://uark-my.sharepoint.com/:w:/g/personal/kaylynnc_uark_edu/ESHMw7HI5JJMid5sQyZtV30BV_TZ-R5Kv9eufZzy3k7t6w?e=z3PTlM
