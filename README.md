# Used Car Price Prediction using Machine Learning
## Project Overview
This project develops an end-to-end Machine Learning system that predicts the selling price of a used car in Pakistan based on its specifications.

The model was trained using a real-world dataset collected from PakWheels, Pakistan's largest online automobile marketplace. After training and evaluating multiple regression algorithms, the best-performing model was deployed as an interactive Gradio web application, allowing users to estimate a car's market price by entering its details.

### This project demonstrates the complete Machine Learning pipeline including:

•	Data Cleaning                                                                                                      
•	Exploratory Data Analysis (EDA)                                                                                  
•	Feature Engineering                                                                                              
•	Text Processing (NLP)                                                                                            
•	Feature Scaling                                                                                                  
•	Categorical Encoding                                                                                              
•	Model Training                                                                                                  
•	Model Evaluation                                                                                                  
•	Model Serialization                                                                                              
•	Interactive Web Application Deployment using Gradio   
### Make a function for NLP
Natural Language Processing (NLP) was applied to the Company & Model and Features text columns using a custom preprocessing function to clean and normalize textual data.                                        
The processed text was transformed into machine-learning-ready features, enabling the model to better understand vehicle specifications and improve car price prediction accuracy.
## Objectives
The main objectives of this project are:                                                                             
•	Predict the price of a used car accurately.                                                                      
•	Apply complete data preprocessing techniques.                                                                    
•	Compare multiple Machine Learning regression models.                                                              
•	Deploy the trained model into a user-friendly web application.                                                    
•	Save and reuse preprocessing objects for real-world predictions.                                                  
## Repository Structure
Used-Car-Price-Prediction/                                                                                          
•	usedcarpricemodel.py                 # Complete ML model training code                                          
•	appusedcarpricemodel.py              # Gradio Web Application                                                  
•	UsedCarPriceTrainedModel.joblib      # Trained Regression Model                                                   
•	CounterVectorizer.joblib             # Saved CountVectorizer                                                  
•	OneHotEncoder.joblib                 # Saved OneHotEncoder                                                         
•	StandardScaler.joblib            	   # Saved StandardScaler                                                    
•	PakWheelsDataset.xlsx        	       # Dataset                                                                
•	README.md                         	 # Project Documentation                                                    
## Dataset
###  Dataset Source
Pakistan Used Cars Dataset (PakWheels)                                                                            
https://www.kaggle.com/datasets/muhamedumarjamil/pakistan-used-cars-dataset                                      
The dataset contains thousands of used car listings collected from PakWheels.                                      
### Features Used
    Feature          -  Description                                                                                 
•	CompanyModel       - Car Company & Model                                                                         
•	Features           - Car Features (ABS, Airbags, Navigation, etc.)                                             
•	Year               - Manufacturing Year                                                                       
•	Mileage            - Total Driven Distance                                                                       
•	Engine Capacity    - Engine Size (CC)                                                                           
•	Fuel               - Petrol, Diesel, Hybrid, etc.                                                                 
•	Transmission       - Automatic / Manual                                                                           
•	Province           - Province                                                                                     
•	Color              - Car Color                                                                                     
•	Assembly           - Local / Imported                                                                             
•	Body               - Type  Hatchback, Sedan, SUV, etc.                                                            
### Target Variable 
Price                                                                                                              
## Exploratory Data Analysis (EDA)
The dataset was explored using different visualization techniques.                                                  
### Performed analysis includes:
•	Dataset inspection                                                                                                
•	Missing value analysis                                                                                            
•	Duplicate removal                                                                                                  
•	Feature distributions                                                                                            
•	Pie Charts                                                                                                        
•	Bar Charts                                                                                                        
•	Descriptive Statistics                                                                                          
•	Numerical summary                                                                                              
#### Examples:
•	Fuel distribution                                                                                                
•	Transmission distribution                                                                                        
•	Assembly distribution                                                                                            
•	Engine Capacity statistics                                                                                      
•	Mileage statistics                                                                                                
•	Price statistics                                                                                                  
## Data Preprocessing
Several preprocessing steps were performed before training.                                                        
### 1. Missing Values
Removed rows containing missing values.
### 2. Duplicate Records
Duplicate rows were detected and removed.
### 3. Text Cleaning
Two text columns were cleaned:                                                                                      
•	CompanyModel                                                                                                      
•	Features                                                                                                          
#### The following NLP preprocessing techniques were applied:
•	Convert text to lowercase                                                                                        
•	Tokenization                                                                                                    
•	Remove punctuation                                                                                                
•	Remove special characters                                                                                        
•	Remove English stopwords                                                                                          
•	Porter Stemming                                                                                                    
### 4. Text Vectorization
Text data was converted into numerical features using : CountVectorizer                                              
Vectorized Columns:                                                                                               
•	CompanyModel                                                                                                      
•	Features                                                                                                        
### 5. Feature Scaling
Numerical columns were standardized using : StandardScaler                                                        
Scaled Features:                                                                                                    
•	Year                                                                                                              
•	Mileage                                                                                                           
•	Engine Capacity                                                                                                
### 6. Categorical Encoding
Categorical variables were transformed using : OneHotEncoder                                                        
Encoded Features:                                                                                                    
•	Fuel                                                                                                              
•	Transmission                                                                                                      
•	Province                                                                                                          
•	Color                                                                                                         
•	Assembly                                                                                                          
•	Body Type                                                                                                        

Unknown categories are safely handled using : handle_unknown='ignore'
### 7. Feature Combination
Finally, all processed features were combined:                                                                      
•	Vectorized Text Features                                                                                          
•	Scaled Numerical Features                                                                                        
•	One-Hot Encoded Categorical Features                                                                            
into one final feature matrix used for training.                                                                  
## Machine Learning Models
Multiple regression algorithms were tested.                                                                         
Examples include:                                                                                                    
•	Decision Tree Regressor                                                                                            
•	Random Forest Regressor                                                                                          
•	Linear Regression                                                                                                
•	Ridge Regression                                                                                                
•	Lasso Regression                                                                                                  
•	CatBoost Regressor                                                                                                 
Different models were compared using standard regression evaluation metrics.
## Model Evaluation
The models were evaluated using:                                                                                  
•	Mean Absolute Error (MAE)                                                                                      
•	Mean Squared Error (MSE)                                                                                          
•	Root Mean Squared Error (RMSE)                                                                                  
•	Mean Absolute Percentage Error (MAPE)                                                                            
After comparison, the best-performing model was selected and saved using : Joblib.                                 
## Saved Objects
To ensure identical preprocessing during prediction, the following objects were saved.                            
•	UsedCarPriceTrainedModel.joblib                                                                                
•	CounterVectorizer.joblib                                                                                        
•	OneHotEncoder.joblib                                                                                              
•	StandardScaler.joblib                                                                                              
This guarantees that the application preprocesses new user input exactly the same way as the training data.          
## Gradio Web Application
An interactive web application was developed using : Gradio.                                                        
Users can enter:                                                                                                
•	Company & Model                                                                                                    
•	Car Features                                                                                                    
•	Year                                                                                                            
•	Mileage                                                                                                          
•	Engine Capacity                                                                                                    
•	Fuel Type                                                                                                        
•	Transmission                                                                                                      
•	Province                                                                                                          
•	Color                                                                                                          
•	Assembly                                                                                                          
•	Body Type                                                                                                        
The application performs:                                                                                          
•	Text preprocessing                                                                                              
•	Vectorization                                                                                                    
•	Feature Scaling                                                                                                  
•	One-Hot Encoding                                                                                                  
•	Feature Combination                                                                                            
•	Price Prediction                                                                                                  
and instantly displays the estimated used car price.                                                                
## Technologies Used
•	Python                                                                                                             
•	Pandas                                                                                                            
•	NumPy                                                                                                            
•	Scikit-Learn                                                                                                      
•	NLTK                                                                                                              
•	Gradio                                                                                                            
•	Joblib                                                                                                          
•	Matplotlib                                                                                                      
## Python Libraries
•	pandas                                                                                                          
•	numpy                                                                                                            
•	scikit-learn                                                                                                      
•	matplotlib                                                                                                      
•	nltk                                                                                                          
•	gradio                                                                                                          
•	joblib                                                                                                            
Install them using : pip install pandas numpy scikit-learn matplotlib nltk gradio joblib                            
## How to Run the Project
### Step 1
Clone the repository : git clone https://github.com/yourusername/Used-Car-Price-Prediction.git                      
### Step 2
Open the project folder.
### Step 3
Install required libraries.
### Step 4
Run the Gradio application.                                                                                          
python appusedcarpricemodel.py
### Step 5
Open the generated local URL in your browser.                                                                        
Enter the required car information and click  Predict  to estimate the car price.
## Machine Learning Workflow
Dataset                                                                                                   
   │                                                                                                      
   ▼                                                                                                      
Data Cleaning                                                                                             
   │                                                                                                       
   ▼                                                                                                      
EDA                                                                                                        
   │                                                                                                       
   ▼                                                                                                       
Text Processing                                                                                           
   │                                                                                                       
   ▼                                                                                                      
Count Vectorization                                                                                       
   │                                                                                                      
   ▼                                                                                                      
Feature Scaling                                                                                           
   │                                                                                                      
   ▼                                                                                                      
One Hot Encoding                                                                                
   │                                                                                                       
   ▼                                                                                                      
Feature Combination                                                                                        
   │                                                                                                       
   ▼                                                                                                      
Model Training                                                                                             
   │                                                                                                       
   ▼                                                                                                       
Model Evaluation                                                                                          
   │                                                                                                      
   ▼                                                                                                       
Save Model                                                                                                
   │                                                                                                      
   ▼                                                                                                      
Gradio Web Application                                                                                    

## Educational Purpose
This repository was developed as an academic Machine Learning project to demonstrate practical implementation of:                                                                                        
•	Data Preprocessing                                                                                    
•	Feature Engineering                                                                                    
•	Natural Language Processing (NLP)                                                                
•	Regression Models                                                                                    
•	Model Deployment                                                                                       
•	Interactive Web Applications                                                                           
It can serve as a learning resource for students studying Machine Learning and Data Science.
## Future Improvements
Possible future enhancements include:                                                                    
o	Hyperparameter Optimization                                                                            
o	XGBoost Regressor                                                                                    
o	LightGBM Regressor                                                                                    
o	Model Explainability using SHAP                                                                        
o	Feature Importance Visualization                                                                    
o	Cloud Deployment (Hugging Face Spaces / Render / Railway)                                              
o	REST API using FastAPI or Flask                                                                    
o	Streamlit Dashboard                                                                                
o	Automatic Retraining Pipeline                                                                    
## Author
Maqsood Ahmad                                                                                            
Machine Learning | Python | Data Science                                                                
## Acknowledgements                                    
Special Thanks to my teachers Mr. Zafar Iqbal and Mr. Hisham Sarwar & also                            
o	Kaggle                                                                                            
o	PakWheels                                                                                        
o	Scikit-Learn                                                                                        
o	NLTK                                                                                                
o	Gradio                                                                                            
o	Python Community                                                                                    
If you found this project useful, please consider giving it a ⭐ on GitHub.                            
