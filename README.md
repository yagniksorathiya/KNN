# KNN

## Problem Statement 

**Zoo :**

Implement a KNN model to classify the animals in to categorie

**Glass:**

Prepare a model for glass classification using KNN

# ➳ What is KNN?

K Nearest Neighbour is a simple algorithm that stores all the available cases and classifies the new data or case based on a similarity measure. It is mostly used to classifies a data point based on how its neighbours are classified.

# ➳ How shall I choose the value of k in KNN Algorithm?

'k’ in KNN algorithm is based on feature similarity choosing the right value of K is a process called parameter tuning and is important for better accuracy. Finding the value of k is not easy.

## ↳ Few ideas on picking a value for ‘K’

![idea_innovative](https://github.com/yagniksorathiya/KNN/assets/129974278/47a6964e-7cba-4269-be1f-0f87ed8248ac)

1) There is no structured method to find the best value for “K”. We need to find out with various values by trial and error and assuming that training data is unknown.

2) Choosing smaller values for K can be noisy and will have a higher influence on the result.

3) Larger values of K will have smoother decision boundaries which mean lower variance but increased bias. Also, computationally expensive.

4) Another way to choose K is though cross-validation. One way to select the cross-validation dataset from the training dataset. Take the small portion from the training dataset and call it a validation dataset, and then use the same to evaluate different possible values of K. This way we are going to predict the label for every instance in the validation set using with K equals to 1, K equals to 2, K equals to 3.. and then we look at what value of K gives us the best performance on the validation set and then we can take that value and use that as the final setting of our algorithm so we are minimizing the validation error .

5) In general, practice, choosing the value of k is **k = sqrt(N)** where N stands for the number of samples in your training dataset.

6) Try and keep the value of k odd in order to avoid confusion between two classes of data.

# ➳ How does KNN Algorithm works?

In the classification setting, the K-nearest neighbor algorithm essentially boils down to forming a majority vote between the K most similar instances to a given “unseen” observation. Similarity is defined according to a distance metric between two data points.

While there are several distance measures that you can choose from, this article will only cover the following:

+ **Euclidean distance (p=2):** This is the most commonly used distance measure, and it is limited to real-valued vectors. Using the below formula, it measures a straight line between the query point and the other point being measured.

![Euclidean Distance](https://github.com/yagniksorathiya/KNN/assets/129974278/11e15926-9a9c-46cd-94ad-017fa0f2d763)

+ **Manhattan distance (p=1):** This is also another popular distance metric, which measures the absolute value between two points. It is also referred to as taxicab distance or city block distance as it is commonly visualized with a grid, illustrating how one might navigate from one address to another via city streets.

![Manhattan Distance](https://github.com/yagniksorathiya/KNN/assets/129974278/c47a55cf-e5cd-42c2-aa6a-994ec7263007)

+ **Minkowski distance:** This distance measure is the generalized form of Euclidean and Manhattan distance metrics. The parameter, p, in the formula below, allows for the creation of other distance metrics. Euclidean distance is represented by this formula when p is equal to two, and Manhattan distance is denoted with p equal to one.

![minkowski](https://github.com/yagniksorathiya/KNN/assets/129974278/2d588ac3-f766-4c62-b993-4ce38b7985ba)

+ **Hamming distance:** This technique is used typically used with Boolean or string vectors, identifying the points where the vectors do not match. As a result, it has also been referred to as the overlap metric. This can be represented with the following formula:

![Hamming Distance](https://github.com/yagniksorathiya/KNN/assets/129974278/80631591-9737-448f-84da-43755448d59d)

# ➳ Advantages and disadvantages of the KNN algorithm

Just like any machine learning algorithm, k-NN has its strengths and weaknesses. Depending on the project and application, it may or may not be the right choice.

## ↳ Advantages

- **Easy to implement:** Given the algorithm’s simplicity and accuracy, it is one of the first classifiers that a new data scientist will learn.

- **Adapts easily:** As new training samples are added, the algorithm adjusts to account for any new data since all training data is stored into memory.

- **Few hyperparameters:** KNN only requires a k value and a distance metric, which is low when compared to other machine learning algorithms.

## ↳ Disadvantages

- **Does not scale well:** Since KNN is a lazy algorithm, it takes up more memory and data storage compared to other classifiers. This can be costly from both a time and money perspective. More memory and storage will drive up business expenses and more data can take longer to compute. While different data structures, such as Ball-Tree, have been created to address the computational inefficiencies, a different classifier may be ideal depending on the business problem.

- **Curse of dimensionality:** The KNN algorithm tends to fall victim to the curse of dimensionality, which means that it doesn’t perform well with high-dimensional data inputs. This is sometimes also referred to as the peaking phenomenon, where after the algorithm attains the optimal number of features, additional features increases the amount of classification errors, especially when the sample size is smaller.

- **Prone to overfitting:** Due to the “curse of dimensionality”, KNN is also more prone to overfitting. While feature selection and dimensionality reduction techniques are leveraged to prevent this from occurring, the value of k can also impact the model’s behavior. Lower values of k can overfit the data, whereas higher values of k tend to “smooth out” the prediction values since it is averaging the values over a greater area, or neighborhood. However, if the value of k is too high, then it can underfit the data. 
