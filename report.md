# Overview

This analysis provides a neural network model to classify the sucesss of charity funding. 

# Summary 
The model was found to perform relatively poorly even after several attempts at optimzation (< 75% accuracy, highest 74%). The simpler models did not see a signiciantly reduced performance compared to more complex NN models

# Results

## Data Preprocessing
* Target Variable: "IS_SUCCESSFUL" binary classification
* Features: 
	* **One hot encoded**: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE	ORGANIZATION, INCOME_AMT, SPECIAL_CONSIDERATION. 
	* **Scaled**: ASK_AMT
* **Removed variables**:  Status. Found to provide an increase in performance

## Performance
No model was sucessful in reaching 75% accuracy. 

More more sucessful models were found to have 72-73% accuracy. The models with 72.9% accuracy (218 neurons in 2 layers) are much more complex than a comparatively very simple model with 72.5% accuracy (28 neurons in 2 layers). A much more complex model with 426 neurons in 4 layers was found to have 72.9% accuracy as well.

The final model selected was the simpler model with 72.5% performance beacuse it had very similar accuracy to the much more complex models, and completed training much faster.

## Optimiations attempted

Manual optimization was done with smaller models. 

Removing features was attempted. Small improvement was found in removing the Status column.

Adjusting epoch was attempted. It was found that models did not improve after ~75 epochs.

Adjusting neuron count was attempted from 4 to 256, for marginal improvement.A low neuron count was selected.

Adjusting layer count from 1 to 4 was done. A 2 layer system was selected as in 3 or 4 layers the improvements were marginal.

Adjusting the activation function between sigmoid, tanh, and relu was found to significant improvements in the inner layers. relu was selected.

## Next Steps

The next step I would take to improve this model is to do an analsys using unsupervised learning to give insight into the importance of different features. I might use PCA to become more informed about which features could be removed or what the dimensionallity of this problem is. 

I would use a nearest neighbors model to group the similarities of sucessful funding asks. This type of problem has a distinct set of sucessful conditions, and more ways to be unsucessful. I think a nearest neighbors models would be good at predicting the successful cases. I asssume the business problem that is trying to be solved is to identify sucessful cases for ease of processing, and identifying unsucessful cases to allot more attention to them.