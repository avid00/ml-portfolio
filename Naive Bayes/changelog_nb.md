Changes:

1. added my own dataset from sdss (https://www.kaggle.com/datasets/amydas/sdss-medium-sized-data) source: https://www.kaggle.com/datasets/fedesoriano/stellar-classification-dataset-sdss17

2. added sklearn.model_selection.train_test_splits to split the dataset into training and testing sets.

3. features are assigned as follows:
features = ['u', 'g', 'r', 'i', 'z']
X = data[features]
y = data['class']
 
4. results were not that great and 'i'i feature had extreme outliers, so I reran gaussianNB without feature i

5. the results still weren't that great with Gaussian NB when looking at the confusion matrix so I added tried adding 2 more NB methods:
    a. MultinomialNB 
    b. BernoulliNB

6. Multinomial NB gave error of negative values so i tried normalising the values but it sitll didn't work and I realised it is not the best method for this type of data as it cant work well with negative values

7. proceeding with gaussianNB and multinomialNB. 

8. removed bernoulli after reading up more about it. It assumes binary values so removed that too. proceeding with gaussian alone and tweak it to work better.

9. Changing features did not yield promising results. After looking into it I realised that GaussianNB assumed features are normalised, so I am going to normalise the features and do it again.

10. for fine tuning the model:
    a. removing outliers with z score from scipy
    b. standardizing features for GNB
    c. adding selectkbest library to select 3 best features instead of manual feature selection
    d. tuning the model:
        d.1. adding var_smoothing for best smoothing value

11. This still didn't yield the results I wanted so I studied more and realised I was using the wrong dataset.

12. Switching dataset to 