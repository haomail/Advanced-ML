# Advice for Applying Machine Learning
## Deciding what to try next
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/618deeaf-d3da-4a75-a0da-9fda4426735d">
Regularization: attempt to reduce the impact of all the features (mostly used to reduce overfitting)
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/477449e1-218c-4e61-a353-2f8e187f7ed4">

## Evaluating a model
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/037af636-7eb2-47ed-ac16-75c5be68db97">
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/e67728c6-855f-412b-9fcf-02fc89c5a8b1">
<p> We can split our entire data into 70 (training) : 30 (test) or 80 (training) : 20 (test). <br>
  But 7:3 is commonly used in ML.
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/c5eed058-641a-443d-b2f2-229d31806128">
when we want to compute the test and training error, we dont have to include the regularization term.

<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/cbd3332c-c17f-42b6-a9e0-1b781cd20a85">
<p>
  On overfit model, Jtrain will be low because the average error of training examples will close to 0. <br>
  If we add the additional test on our model that hadnt trained on, there will be a large gap between the predict value and the actual value. 
  So, Jtest will be high. It means that the model is good on training set, it doesnt so good when generalizing new data that were not on training set.
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/8cef8728-e3a7-4b58-8957-a194481ca477">
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/20a1d21a-deee-4176-ba6c-76cbff52963e">
<p>
  Instead of using the logistic loss, we can measure the fraction of the test set and training set that the algorithm has misclassified. <br>
  Define the treshold of the output of y-test and count all the fraction that isnt equal to the actual ground truth label (missclasified). <br>
  ex: 0 was classified as 1 <br>
  Also the fraction of the train set that has been misclassified.
</p>

## Model selection and training/cross validation/test
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/31fdf2ef-a236-46fb-9f9f-77987343eaa9">
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/20718647-8797-46f3-a2e7-8e4f90f8962b">
<p>
  Jtest to estimate how well does the model generalize the new data. <br>
  d = degree of the polynomial. <br>
  We can see through all of the Jtests and see which one gives us the lowest value. <br>
  Choose the model (d) that gives us lowest value and apply that to our application. <br>
  Our lowest Jtest is an optimistic estimate of generalization error. It slightly lower than the actual generalization error. <br>
  But this method is flawed and the instructor dont reccomend us to using this. <br>
</p>

<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/cf880791-cb22-4fe0-8ee8-3c71a3f636c5">
<p>
  Instead of splitting our data into training set and data set, we can split into training set, cross-validation set and test set. <br>
  60 (training set) : 20 (cross-validation set) : 20 (test set) <br>
  Cross-validation test: to check/crosscheck the validity or the accuracy of the different models.
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/e502b1f0-4ea6-4bb1-8840-6eb7651d4012">
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/f7118d4b-2c83-4329-af3e-4c0b6063edd5">
<p>
  Evaluate the parameters using cross-validation set. <br>
  Choose the model that has the lowest cross-validation error. <br>
  Report the estimate of generalization error using the third subset, test set. 
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/fd168d08-0681-4f31-97fc-c0d6043d5344">
<p>
  We can decide how many layers and hidden unit we want to have using model selection. <br>
  Train the model first, then evaluate the neural network performance using Jcv (the fraction that misclassified). <br>
  Pick the model with the lowest cross-validation error. <br>
  Use the test set to estimate how wellthe neural network that our chose will do.
</p>
