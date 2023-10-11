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

# Bias and Variance
## Diagnosing Bias and Variance
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/ba1fdfd2-2c7c-4d9e-98ba-657b7c16e624">
<p>
  We can diagnose our model if there are high variance/bias by looking at the performance on training set and cross validation set. <br>
  Jtrain: How well does the algorithm do on the training set? (Bias indicator) <br>
  - High: Pretty large errors between the examples and the actual predictions of the model (Not doing well on training set). <br>
  - Low: Fits the data training really well. <br>
  Jcv: Adding few examples that the algorithm had not previously seen. (Variance indicator) <br>
  - High: Algorithm doesn't do that well on the examples that not previously seen. <br>
  - Low: Do well on the examples that not seen before.
  High bias (underfit): High Jtrain and Jcv. <br>
  High variance (overfit): Low Jtrain, High Jcv. Jcv >> Jtrain. <br>
  "Just right": Low Jtrain and Jcv.
</p>

<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/c65d3e4f-867f-4baf-8ae0-eb15da08bf3f">
<p>
  The lower our degree of polinomial, Jtrain and Jcv will be high. The model will underfit (high bias). <br>
  The higher our degree of polinomial, Jtrain will be low and Jcv will be high. (Jcv >> Jtrain). The model will overfit (high variance). <br>
  If we choose between that (in the middle), we got low Jtrain and Jcv. That's the good model. <br>
</p>

<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/1ed39d76-9286-49bc-8f56-6ec428b54a42">
<p>
    Special occasion: <br>
  High bias and high variance: Overfit to the parts of the input and underfit the parts of the input. <br>
  - Jtrain will be high and Jcv >> Jtrain.
</p>

## Regularization and Bias/Variance
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/78bce06b-8ffa-4281-ab65-4514853c3dbb">
<p>
  Lambda (regularization parameter): control how much trade of we keep the parameters w small vs fitting the training data well. <br>
  - If lambda is LARGE, w parameters will be very small and close to 0. <br>
     - f(x) will be a constant value (b). <br>
     - The model has high bias (underfit), Jtrain is large. <br>
  - If Lambda is SMALL, example = 0. There is no regularization. <br>
     - Ended up with wiggly curve that overfits the data. <br>
     - The model has high variance (Jtrain is small, Jcv is large). <br>
  - If Lambda is INTERMEDIATE, just right and fits the data well. <br>
     - Jtrain and Jcv is small.
</p>

<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/7eb1d8ef-60a0-406e-a6ad-4b02625cc2db">
<p>
  How to choose a good value of Lambda to use for regularization parameter? by cross validation. <br>
  1) Trying out the large of possible values for Lambda. <br>
  2) Fitting parameters using different regularization parameters. <br>
  3) Evaluating of cross validation set. <br>
  4) Pick the best value for the regularization parameter. <br>
  - We got the fifth iteration that has the lowest cross validation set, pick this value as the lambda and use w5, b5 as chosen parameters <br>
  - Report the test error, use Jtest of w5 and b5. 
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/49d0e4f2-0a5d-463c-8969-09f280384f61">

## Establishing a Baseline Level of Performance

## Learning Curves

## Deciding What to Try Next Revised

## Bias/Variance and Neural Networks
