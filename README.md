# Malaria Detection by Using K-Means Algorithm

![alt text](https://cdn1.sph.harvard.edu/wp-content/uploads/2015/03/Malaria-cells_CDC.jpg)

### What is Malaria
Malaria is a life-threatening disease caused by parasites transmitted to people
through the bites of infected female Anopheles mosquitoes. Malaria is preventable and curable.

### Goal
This project was created to enable identification of disease through automated reading of images of tissues with either infected or parasite-free cells. 
The dataset was taken from https://www.kaggle.com/iarunava/cell-images-for-detecting-malaria.

![alt text](https://cdn-images-1.medium.com/max/1000/1*uge32yBp6GWmAVn_ZdxGCA.png)

### What is K-Means Algorithm
The k-means algorithm divides data into k number of clusters and then, by calculating distances
between new data and centroid, finds which centroid each image refers to.
https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1.

### Data Preparation
First of all, each image was converted from RGB into white and black format (8-bit color, from 0 to 256).
Then, the histogram was taken and stored in the array. Next, each histogram was equalized to obtain better accuracy.
https://docs.opencv.org/2.4/doc/tutorials/imgproc/histograms/histogram_equalization/histogram_equalization.html.

### K_Means Part
https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1.
Each picture's histogram has 256 digits that represent the number of pixels of the single code (0-256).
For k-means we used 256-dimensional space, where each picture represents a point of 256 number of coordinates.
The number of centroids was set to 2 (for parasitized and uninfected). Finally, the whole data was processed 
by the algorithm, which outputs two centroids.

### Prediction
For prediction, a new picture was taken, converted into black and white, equalized, and used to obtain a point of 256 coordinates.
Then, by looking at which centroid was the picture's histogram the closest (by euclidian distance), we could find its reference cluster. This told us whether or not the image contained parasitized cells. Finally, repeating the prediction algorithm, we could find its reference class.

### Conclusion
The accuracy of prediction was insufficient for functional use. 
The k-means algorithm was not good for image classification. For more algorithms, one can look
to the kaggle kernels of malaria detection https://www.kaggle.com/iarunava/cell-images-for-detecting-malaria.
To increase predicting accuracy, the following adaptations were made: 
  - Color of # 0 was eliminated from all images, because of the color’s extreme variation.
  - Histograms were equalized.
  - The number of training data was increased.

In the end, the accuracy did not increase sufficiently.

### Requirements
OpenCV, NumPy, Pandas, Matplotlib
```bash
$ pip install -r requirement.txt
```
### License

**Free Software, Hell Yeah!**
