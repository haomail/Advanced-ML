# Neural Network Training
## TensorFlow Implementation
  <img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/fbe815d6-12e3-4edb-a1f8-3eefac8ae600">
  <p> Step 1 is to specify the model, which tells TensorFlow how to compute for the inference. <br>
  Step 2 compiles the model using a specific loss function, and step 3 is to train the model. </p>

## Training Details
  <img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/bf7b385e-792c-4877-b380-d84aad3e6c24">
   <p> Step 1: of building a logistic regression model was you would specify how to compute the output given the input feature x and the parameters w and b. <br>
  Step 2: do to train the literacy regression model was to specify the loss function and also the cost function. <br>
  - Loss function measure of how well is logistic regression doing on a single training example x comma y. <br>
  - Cost function J is an average of the loss function computed over your entire training set. <br>
  Step 3: to train a logistic regression model was to use an algorithm specifically gradient descent to minimize that cost function J of WB to minimize it as a function of the parameters W and B. </p>
  
  <img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/c7eeb7a8-4f06-4a7a-829a-51679e175962">
  <p> Step one is specify how to compute the output given the input x and parameters W and B. <br>
  It tells you that there are 25 hidden units in the first hidden layer, then the 15 in the next one, and then one output unit and that we're using the sigmoid activation value. </p>
  
  <img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/55f2e90d-04b4-4908-ad74-5f1c07ecd42d">
  <p>The second step is to compile the model and to tell it what loss you want to use. <br>
    The binary cross entropy loss function taking an average over the entire training set also gives you the cost function for the neural network. The output is either 0 or 1. <br>
    If we have a regression problem and want to minimize the squared error loss, we can use the squared error loss. </p>

  <img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/edf23f6c-de81-4abd-b4ff-05749f47c3b8">
  <p> Step three is to call function to try to minimize the cost as a function of the parameters of the neural network. <br> 
  At first, we use gradient descent to train the parameters of a neural network. <br>
  In Neural Network, we use backpropagation algorithm in order to compute these partial derivative terms. <br> 
  We can call model.fit, x, y as our training set, and tell it to do so for 100 iterations or 100 epochs.</p>
  <img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/13bb0310-265e-464f-83cb-946fdf028f9c">

# Activation Functions
## Alternatives to the Sigmoid Activation
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/b006da21-fc00-4010-a7b4-8a066d1bc1ad">
<p> Sigmoid: Output goes between 0 and 1 <br>
Rectified Linear Unit (ReLU): If z < 0 then g(z) is 0. If z > 0 then g(z) is z. <br>
- g(z) = max(0,z) <br>
Linear Activation Function: g(z) = z.</p>
  
## Choosing Activation Functions
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/3ddfc997-cc99-4759-87f0-0b3030c39afd">
<p> Output layer <br>
- binary classification problem, use sigmoid. <br>
y = 0/1 <br>
- regression problem, ex stock price, use linear activation function <br>
y = +/- <br>
- regression problem, ex price of the house, use ReLU <br>
y >= 0</p> <br>

<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/77fde968-e2cf-4d5f-8ac6-b80b236c9652">
<p> Hidden Layer <br>
  Most common choice: ReLU <br>
  Why? <br>
  - ReLU is a bit faster to compute <br>
  - ReLU goes flat only in one part of the graph <br>
  - Fast learning when using gradient descent <br>
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/74214575-ab52-433e-9035-607cdd0f625e">

## Why do we need Activation Functions?
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/16218822-2b26-4c77-a5fb-fc4c7808a292">
 
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/ad9e453a-1753-4b30-baea-742bfc1a9f02">
 
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/5dcb7f29-7e80-49fa-96b8-a1f291b82eb1">
<p>
  If we were to still use a linear activation function for all the hidden layers and a logistic activation function for the output layer, then it turns out you can show that this model becomes equivalent to logistic regression.
</p>

# Multiclass Classification
## Multiclass
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/7d801d24-901d-4ad2-a822-e4079c710acd">
<p> Multiclass classification: More possible outputs so not just 0 or 1.</p>

<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/f9aa446a-c0ee-4df6-ac87-77de860d5d4f">
<p> We can have more classes to be classified and using boundary to separate them.</p>

## Softmax
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/22cb65ca-3ff4-4049-a7e4-77580c54bff2">
<p> With softmax regression, we can have more possible outputs. <br>
Sum of all the activation function is up to 1. Because each of the activation function is a probability of 1/2/3/4 given by x. </p>

<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/f113cb6b-ea56-4ec9-89ee-4f1f1f957887">
<p> Softmax regression only uses the left side of logistic regression loss, that is -y log a1. But we only take the -log a1 part of it.</p>

## Neural Network with Softmax Output
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/b82dd9f6-ab15-4137-9cb9-66db3c857dc7">
<p> a's from softmax output depends on all the z's output.</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/c3cbecdd-9354-4fff-9f3a-af88a4ec25c5">
<p> SparseCategoricalCrossentropy: we're still classified y into categories. <br>
- sparse refers to that y can only take on one of these 10 values.</p>

## Improved Implementation of Softmax
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/fb880b31-5da7-458e-ac7a-e18543109bad">
<p>
  We can avoid numerical roundoff errors by using the formula directly, without the intermediate term "a" (if we allow TF to do so). Because in softmax, this roundoff error could get worse. <br>
  If we specify the equation directly, then TF can rearrange terms in this expression and come up with a more numerically accurate way to compute this loss function. It gives TF more flexibility in terms of how to compute this and whether or not it wants to compute a explicitly. <br>
  logits = z as an intermediate value that can rearrange terms to make this become computed more accurately.
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/76bec459-3391-4eaf-bda1-8628851fc9a7">
<p>
  If we specify the loss, TF can rearrange terms and compute this integral numerically accurate way. <br>
  Why? If z is a very large number, then e to the z can become a very large number and by rearranging terms, TensorFlow can avoid some of these very small or very large numbers and therefore come up with more actress computation for the loss function.
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/bc3b929a-5791-498e-aeee-5a3e9c1d2a6e">
<p>
  We've changed the output layer using linear activation. We put z_1 through z_10 through it.
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/44a76105-7c1e-4aa7-8d90-1a7901727f7f">
<p>
  For logistic regression, we have to change to code in order to get the output value and map it through the logistic function in order to actually get the probability.
</p>

## Classification with Multiple Outputs
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/841e6b41-d7e1-441c-96be-37a5b09bba5f">
<p>
  Multi-label classification problem: Where associate of each image, they could be multiple labels. 
  Associated with a single input, image X are three different labels corresponding to whether or not there are any cars, buses, or pedestrians in the image. The target of the Y is actually a vector of three numbers (distinct from multi-class classification)
</p>
<img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/15e6df87-1810-4290-8338-e400cec36d38">
<p>
  We can train a single neural network to simultaneously detect all three of cars, buses, and pedestrians. The output  is going to be a vector of three numbers. We can use a sigmoid activation function for each of these three nodes in the output layer, corresponding to the output of cars, buses, and pedestrians.
</p>



