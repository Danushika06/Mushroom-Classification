# **🌟Mushroom Classification Application**<br>

## **Welcome to the Mushroom Classification Application**<br>
A user-friendly tool that leverages machine learning to classify mushrooms as edible or poisonous based on key features like cap shape, gill size, odor, and habitat.<br>

## **🚀 Features**<br>
✨ Real-Time Predictions
<br>Quickly predicts whether a mushroom is edible or poisonous using pre-trained machine learning models.
<br>

✨ Interactive Design
<br>Smooth transitions, user-friendly layout, and clean styling enhanced with dynamic animations.
<br>

✨ Custom Styling
<br>A visually appealing design with a gradient background and modern UI elements for a premium experience.
<br>

## **🛠️ Technology Stack**<br>
Frontend: Streamlit<br>
Machine Learning: Scikit-learn<br>
Preprocessing: Data scaler and encoders (Pickle files)<br>
Programming: Python
<br>

## **💻 Installation Guide**<br>
Clone the repository:<br>

    git clone https://github.com/your-repository/mushroom-classification.git  
    cd mushroom-classification
<br>
Install dependencies: 
<br>


    pip install -r requirements.txt  
<br>
Run the application:<br>


    streamlit run app.py  
<br>

## **🧪 How It Works**<br>
Input Mushroom Features: Enter features like cap-surface, odor, gill-spacing, and more.

Scaled Data: Inputs are preprocessed using a preloaded scaler for accuracy.

Prediction: A trained ML model predicts whether the mushroom is edible or poisonous.

Result: The classification result is displayed prominently on the screen.
<br>

## **💂️‍♀️ Project Structure**<br>

    📁 mushroom-classification/  
    ├── app.py                  # Main application code  
    ├── mushroom_model.pkl      # Pre-trained ML model & preprocessors  
    ├── requirements.txt        # Python dependencies  
    ├── README.md               # Project overview  
<br>

## **🌈 Application Layout**<br>

### **📊 Prediction Section**
Input Fields: Specify mushroom features such as cap-surface, odor, gill-size, and habitat.<br>

Predict Button: Get an instant classification result.<br>

Responsive Design: Works across different screen sizes.<br>
<br>
## **✨ Workflow**<br>
Data Preprocessing<br>

Input features are scaled using StandardScaler.
Labels are encoded using LabelEncoder.
<br>

Model Training
The Random Forest Classifier is used for training the model.
Data is split into training and testing sets (80/20).
<br>

Model Saving
The trained model is saved as a .pkl file using pickle.
<br>

Deployment
The web UI is built using Streamlit to take user inputs for mushroom features.
The trained model is loaded to predict and display classification results.
<br>

## **🚀 Execution**<br>
Train the Model

    python train_model.py  
This script:<br>

Loads and preprocesses the data.<br>
Trains the Random Forest model.<br>
Saves the model as mushroom_model.pkl.
<br>

Start the Streamlit Web App

    streamlit run app.py  
Interact with the Web App<br>

Input mushroom features such as odor, cap-color, and habitat.
Click on "Predict Mushroom Classification" to see the result.<br>

## **🚧 Future Enhancements**<br>
✅ Add real-time mushroom identification via image inputs (using Computer Vision).<br>
✅ Incorporate visual guides for mushroom classification.<br>
✅ Include comparison with known mushroom datasets for better insights.<br>

## **📜 License**<br>
This project is licensed under the MIT License. See the LICENSE file for more information.<br>

## **🌟 Acknowledgments**<br>
Special thanks to Streamlit and Scikit-learn for their powerful tools, and to all those who contributed to the development of this application.
<br>

## **🚀 Get started today and make mushroom identification safer and easier!**
