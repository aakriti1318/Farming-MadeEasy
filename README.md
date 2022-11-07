#Farming Made Easy

Farming MadeEasy is an easy-to-use web platform developed powered by the SingleStore DB for the farmer to predict the better suitable crop for a particular location.
The key features are:
1. Recommend the user the optimal crop to cultivate based on several parameters for given soil and weather conditions. 
2. Provide easy usage to one seamless user interface powered by an interactive open-source map to easily navigate to the desired location.

## How we built it
1. **Machine Learning Model:**
To construct the machine learning model for our project, we used the hyperparameter optimization method to find the right combination of hyperparameter values for the random forest classifier model to achieve maximum prediction accuracy on the data in a reasonable amount of time. 
The dataset provides a label for the optimal crop based on the Nitrogen, Phosphorous, Potassium, Temperature, Humidity, pH, and Rainfall levels that are observed in the environment. There are a total of 22 possible crop labels in the dataset.


2. **Crop Recommendation API:**
The machine learning model trained on the SingleStore DB is saved for future predictions and deployed with the help of the serverless function on the azure function app as an HTTP endpoint. It provides great flexibility to utilize the endpoints in the web or mobile application.

3. **Web Portal:**
The client interface of the application is developed using react. Where we have provided the Map from where Farmers can select the land where they want to see the predictions on the basis of the geo-coordinates. Furthermore, this application fetches the soil properties from the IRSIC - World soil information database & weather conditions such as temperature, relative humidity, and average precipitation from the weatherBit Historical API. All these cumulative parameters get passed to the crop recommendation API to get the most suitable crop for provided the conditions.
![Architecture Diagram](https://d112y698adiu2z.cloudfront.net/photos/production/software_photos/002/286/803/datas/gallery.jpg)
