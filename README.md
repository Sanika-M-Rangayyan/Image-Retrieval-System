# Image-Retrieval-System

This project demonstrates a basic Image Retrieval System with four different variation. This involves using different variations of image search engine based on colour histogram property, feature similarity, extracting features using CNN without the fully connected layer and finally the autoencoder model.

To implement the above, we use the Holiday dataset from kaggle which contains several images of the different holiday destination pictures.

The code in task1_code1 folder follows the process:
- Takes the query image and extracts its features.
- Iterates over the entire database and extracts the feature of each images while comparing the query image features.
- The top 5 similar images are considered.
The above method is not very efficient. There is image feature extraction and comparison on every image when a query image is give. Hence it takes a lot of time to give result.

The code in task1_code2 folder considers the colour composition of the image. To implement this, the colour histogram of the image is considered. This method gave a good results in obtaining images of similar colour composition. This used openCV module to implement the search engine. The description is held in a csv file with one row for every image.
This has a better efficiency in terms for time taken to give the result.


The code in task1_code3 folder is an extension of task1_code1 but better time complexity. It iterates over the entire database before feeding the query image and stores the feature vector in the form of numpy araay(.npy). So, when a new image arrives, it has to compute the feature vector of the query image and implement the similarity index (cosine similarity or eucledian distance) from the  other images by considering the numpy arrays. 
This version also uses a flask application to give a better user interface. The interface takes the query image and on a button click, displays the resulting images.
This produced the results in a better time complexity but uses a very basic way to get the features. These features are just the embeddings of the images with a very conventional way.

The code in task1_code4 folder uses an autoencoder model. The autoencoder model is a type of neural network model which has two components- encode and decoder. The encoder networks takes the image and creates an embedding (also called the latent space). The decoder network takes the embedding produced by the image
