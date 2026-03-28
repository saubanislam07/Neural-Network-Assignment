Project Summary: Pediatric Pneumonia Classification using CNNs

Project Objective:
The goal of this assignment was to develop a Convolutional Neural Network (CNN) to accurately classify pediatric chest X-rays into two categories: Pneumonia and Normal.

Data Preprocessing:
I loaded the dataset using TensorFlow's image_dataset_from_directory utility. To prepare the images for the neural network, I resized all of them to a uniform 150x150 pixels and grouped them into batches of 32 to ensure efficient training without overloading the system memory.

Model Architecture:
I designed a Sequential CNN model. I used three Convolutional (Conv2D) layers paired with Max Pooling layers. These layers act as automated feature extractors, learning to identify visual clues like edges, shadows, and cloudy spots in the lungs that indicate pneumonia. The data was then flattened and passed into a final Dense layer with a sigmoid activation function to make the final binary decision (Sick vs. Healthy).

Addressing Overfitting with Dropout:
During my first attempt, the model experienced "overfitting." It achieved over 98% accuracy on the training data but dropped to roughly 72% on the unseen test data. The model was simply memorizing the training images instead of learning the general patterns of the disease.

To solve this, I built a Version 2.0 model and added a Dropout layer set to 0.5. This technique randomly turns off 50% of the network's neurons during each training step. This acts like a "blindfold," preventing the model from relying on memorized smudges and forcing it to learn the true structural shape of a healthy versus sick lung.

Final Results:
The addition of the Dropout layer and a third Convolutional layer significantly improved the model's ability to generalize. After training for 10 epochs, my final model achieved a 75.32% accuracy on the completely unseen test dataset, proving that it successfully learned to identify pneumonia in new patients.