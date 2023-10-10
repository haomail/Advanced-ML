## Neural Network Training
- TensorFlow Implementation
  <img width="960" alt="image" src="https://github.com/haomail/Advanced-ML/assets/141924190/fbe815d6-12e3-4edb-a1f8-3eefac8ae600">
  <p> Step 1 is to specify the model, which tells TensorFlow how to compute for the inference. <br>
  Step 2 compiles the model using a specific loss function, and step 3 is to train the model. </p>

- Training Details
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

- 
