# End-to-End-Azure-ML-Deployment

### Tools Requirements

1. [Github Account](https://github.com)
2. [VS Code IDE](https://code.visualstudio.com/)
3. [Git CLI](https://git-scm.com/book/en/v2/Getting-Started-The-Command-Line)
4. [Postman](https://www.postman.com)

Create a new environment 

''' 
conda create -p realestate python==3.11 -y
'''

## Dataset

The dataset used for this project contains the following variables:

RealEstate.csv dataset (414)

- `X2 house age`: Age of the house in years 
- `X3 distance to the nearest MRT station`: Distance from the house to the nearest Mass Rapid Transit (MRT) station, in meters. 
- `X4 number of convenience stores`: Number of convenience stores nearby 
- `X5 latitude`: Latitude of the location of the house
- `X6 longitude`: Longitude of the location of the house
- `Y house price of unit area`: Price of the house per unit area (price per square foot or square meter)(target)

## Modeling & Evaluation & Deployment via Azure 

The aim of this project is to deploy a machine learning model using Azure cloud services. For demo purposes, a clean dataset was selected, and only the Random Forest Regressor algorithm was trained. Hyperparameters for the model were optimized using Optuna. 

Learning curve was plotted to conduct a Bias-Variance Analysis. Additionally, the feature importances were visualized to understand the relative importance of each feature in the model's predictions. The performance of the model was evaluated by comparing training and test results based on metrics such as Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), R-squared (R^2), Adjusted R-squared, Mean Absolute Percentage Error (MAPE), and Max Error. [training-notebook](https://github.com/emrecanduran/End-to-End-Azure-ML-Deployment/blob/341fabc39cb6ac2d66afc0571ead278192223bc7/notebooks/training.ipynb)

Furthermore, a single decision tree from the forest was visualized to provide insight into the model's decision-making process. Residuals and prediction error plots were generated to assess the model's performance and identify areas for improvement.

Once the model was trained and evaluated, it was saved as a pickle file and utilized in the deployment process. An application was created using Flask, and Postman was used to obtain predictions via JSON data. The correctness of the predictions was verified in the created app.py file. Finally, the model was deployed via a web application hosted on Azure cloud services, providing users with access to real-time predictions.

### Test API via Postman

![Test API via Postman](https://github.com/emrecanduran/End-to-End-Azure-ML-Deployment/blob/d54c8322f1acbb185d2e331d14437190f2c05c23/screenshots/postman.png)

### Test API via app.py

![Test API via app.py](https://github.com/emrecanduran/End-to-End-Azure-ML-Deployment/blob/94fb0c750ded93cc1002c4728408012e4d3b15d2/screenshots/app.png)

