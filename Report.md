# Deep-learning-challenge

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. A deep learning binary classification neural network model was designed to help Alphabet Soup team towards this purpose.

Model was trained on an existing data comprising of more than 34000 organizations that received funding from Alphabet soup over the years. The data set contained various features for those applications and the target variable `IS_SUCCESSFUL`. Goal was to create a model to help predict the chance of venture success if they are to fund that applicant.


### Pre Processing

Data contained many input features. Some of the features were categorical while some were numerical. Identification features such as `EIN` and `NAME` were removed from the feature selection as they did not add any information and were not relevant in the model training in terms of their relationship to the target variable.

Categorical variables containing large number of categories (>15) were engineered to have fewer categories (< 10) to manage the number of input features. These categorical features were then encoded to numerical values to make them ready for  the model.

Feature variables and Target variable were then separated and the data was split into training data and testing data to evaluate model performance. The numerical feature variables were standardized using `StandardScaler`


### Model Compiling and Training

Model was compiled with an input and a hidden layer and nuber of neurons selected for each layer were 108 as the number of features with `Rectified Linear Unit (RELU)` as activation function.

Output layer has a single neuron with `Sigmoid` activation function toi produce binary output.

Model was compiled using `ADAM` optimizer, loss function as `binary_crossentropy` and `accuracy` metric for model performance evaluation.

Model was initialized with 100 epochs and a call back was configured to save model weights after every 5 epochs.

### Resulta

Over-all  model accuracy was 72.4% and a Loss of 0.56. A target model performance of 75% was not met

### Model Optimization

In order to improve upon the model performance, Kersa model tuner library `keras-tuner` was used to tune the hyper parameters. Hyper parameter search space was configured which included hyperparamaters - 
    * Number of  layers
    * Number of neurons in each layer
    * Activation function
    * Optimizer learning rate
 
Finally tuner was initialized using the tuner class `Hyperband`

Accuracy slightly improved to 73.07% but it still was below the desired 75% level.

### Recommendation

We recould re-look at training data to include more relevant features as to the business experience of the applicant, stage of the venture (early stage, growth etc). We should also evaluate the performance of other binar classifiers such as Logistic Regression, SVM, Ensemble trees etc and compare their performance to choose the model wih best performance


