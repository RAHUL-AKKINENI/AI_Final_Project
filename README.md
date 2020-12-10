# **Disease classifications using chest x-rays** 

Here is the reimplementation of chexnet. Things we done from the paper are

- We build a model in which it takes chest x-ray as the input and outputs the probabilities of 15 classified diseases along with no disease as one of the classification
- How to run and train the models on the GPU’s.we used single Tesla P100 which has taken approx. 22hr give or take to train and load the model and data

**Breakdown of implementation :** 

- We have implemented the dense network(one of the architecture) mentioned in the research paper has been implemented. We have built this model and trained it.
- We have break down the implementation into five stages
1. **Dataset file** 

`                   `First and foremost file being the dataset file  in which data has been loaded. Both the CSV as well as the X-rays both has been stored has data frame. In which labelling of the disease has been specified(which can be seen in the probability table). In this file both the disease affected x-rays are loaded and marked which specific diseases along with the  affected area .

2. **Model file** 

`              `In this file we actually build the model in which dense layers is been used. We also used convolution layers , optimisers required parameter to develop our model   and train it. For more deeper explanation or understanding you can refer to the file along with chexnet paper in which refer to 2.2 Model architecture and training.

3. **Retrain model** 

`                  `In this file we have used the learning rates and weight decays to train our model.for better results and accuracy of the model.

4. **Evaluation model** 

`                     `This file evaluates the predicted  outcome of training file with the actual output of each image.So that that we have a better understanding of the accuracies.  It also stores the weights and predictions of the model which is once complied  on the GPU. There is no need to reiterate the model every time the images are sent  for the classification.  

5. **Visualisation - Prediction model** 

`                                 `In this model name itself says the visualisation in which we overlap the heap map on the X-ray we sent for the classification as the input.we get the output as the heat-maps. Here we can see the colour or heat differents. 

![](AI\_project\_report.001.png)

Heatmap of a x-ray

We get this accurate from the training model. We get the affected area from the heat maps.

**Results:** 

Here left we can see the x-ray as the input where as we can also see the output on the right with heat-map. It signifies the affected area too. There is a prediction table in with labels predicted probability and ground truth.if we give the label of the any 14 disease name we will get the number of review cases having that disease. Along with possibility of any other 14 associated disease.we can have a chance can be seen at predicted probability

Result of the model![](AI\_project\_report.002.png)

**Prediction table analysis:** 

Here looking the particular prediction table.we have given the label = “Infiltration”. Our model predicted to have 2 more diseases like Effusion and Atelectasis with probabilities of 0.7 and 0.4. Other disease doesn’t have ground truth to be true.

Prediction Table ![](AI\_project\_report.003.png)Has other probabilities are too less to be neglected.

**Future works:** 

We use different architectures for this same implementation of disease classification like Facebook net, Alex net and google net. Which will be scope for  different area of research.
