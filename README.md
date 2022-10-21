# Analysis of Charity Donations using Neural Networks

## Overview:
Alphabet Soup's president has asked our data team to put together a mathematical, data-driven model to better predict which organizations are worth donating to and which are too high risk. The complex nature of this binary classification problem has led us to create a deep learning model to better predict investment risk.

## Results:
- **Data Preprocessing:**
  - The target of this model was the "Is Successful" variable. We are trying to accurately predict if our donations will be successfully used by the organizations we donate to. As such, we need to see past successes and failures to train and test this model for its development. 
  - The model features were the variables that described the characteristics of the organizations that would influence their ability to be successful. Variables like APPLICATION_TYPE or ASK_AMT, for example.
  - The identification columns of EIN and NAME were not included as either features or targets. This is because these two variables would not contribute to the predictive power of the model.
   
- **Compiling, Training, and Evaluating the Model:**
  - My initial model used two hidden layers both with relu activation functions. 80 neurons were used on the first layer and 30 on the second. This is partly because I wasn't sure if our initial model structure needed to match the output in the started code file. Additionally, these numbers were also selected due to the rule of thumb of having two to three times the amount of neurons in the hidden layers as the number of inputs, which in this case is 44 features.
  - My initial model achieved an accuracy level of 66%, so it was not able to achieve the target performance of 75%.
 ![Initial_Accuracy](https://github.com/bfox87/Neural_Network_Charity_Analysis/blob/main/Screenshots/Initial_Accuracy.PNG)
  - My first try at optimization actually produced slightly lower results (63%). This resulted when I bumped the neurons on my second layer to 70, added 50 more epochs for a total of 100, and decreased the number of values in the app type and classification bins. My second revision involved adding a third hidden layer with 70 neurons with a relu activation. I also reversed course and increased the number of values to be placed in the 'other' bins with the thought this would reduce some of the noise. It appears this didn't do much as the accuracy dropped slightly to 61%. My third iteration was deciding to go back to original bin sizes and going with a "wide" model. So a lot of neurons (150) in just one hidden layer. I also switched back down to 50 epochs. This improved accuracy to 69%.
 ![Third_Accuracy](https://github.com/bfox87/Neural_Network_Charity_Analysis/blob/main/Screenshots/Third_Accuracy.PNG)

## Summary:
It appears running more epochs did not improve accuracy with my best results coming with 50 epochs over 100. Also, a wide model with just one layer of many neurons worked better. However, I also don't think I properly designed a "deep" model with many layers and fewer neurons per layer. Regardless, I was not able to achieve the target of 75%, falling about 6% below the target. 