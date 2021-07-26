# Knee-Arthritis-Diagnosis-Tool
#### Video Demo: https://www.youtube.com/watch?v=YJBiZYCmvL0
#### Description:
A convolution neural network to diagnose the severity of Osteoarthritis using an X-ray. Provides a confidence for a given knee being in each of the 5 Kellgren-Lawrence(KL) classification tiers.
  
There are 3 different versions, each uses a transfer learning technique based on different models, InceptionResnetV2, VGG16 and VGG19. Each of the files contains a neural network that has been trained on images of various severities of osteoarthritis. They can then take another image and predict how severe the arthritis in the new image is.

The networks automatically alter various parameters to increase its accuracy. These models in particular use [convolution layers](https://www.google.com/url?sa=i&url=https%3A%2F%2Fpeltarion.com%2Fknowledge-center%2Fdocumentation%2Fmodeling-view%2Fbuild-an-ai-model%2Fblocks%2F2d-convolution-block&psig=AOvVaw2VB3q6nkIAEINdpmSXL4c4&ust=1610844060789000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCLikiPObn-4CFQAAAAAdAAAAABAT) to detect specific features in an image.

The small quantity of data available meant that applying random transformations to the data going into th networks during training was very important. This adds variation to the data to help the models generalise more. Also the under represented severities were given greater importance over other classes to account for the data imbalance and reduce bias. 

The knees in the dataset were graded in with the KL system so that is what the networks use. This systems has 5 tiers labelled 0 to 4. 0 =  No osteoarthritis, 1 = Doubtful narrowing of joint space and/or possible osteophytes, 2 = Definite osteophytes and possible narrowing of joint space, 3 = Multiple osteophytes, definite narrowing of joint space and some sclerosis and deformity of bone ends, 4 = Large osteophytes, marked narrowing of joint space, severe sclerosis, and definite deformity of bone ends.

Originally the models output a single number 0-4 of what class it is most confident is correct, however to make the network feel less like a "black box" i changed this to be a bar graph of all confidences.

The data is available here: https://data.mendeley.com/datasets/56rmx5bjcr/1
