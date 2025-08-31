# Churn Predictor App
The Churn Prediction application is an Android application that predicts whether a customer will churn (unsubscribe) or not, based on customer data input.

Experimental Models : 
| Model                    | Accuracy | F1-Score  | Precision | Recall   |
| ------------------------ | -------- | --------- | --------- | -------- |
| Logistic Regression      | 0.78     | 0.78      | 0.78      | 0.78     |
| GaussianNB               | 0.76     | 0.76      | 0.765     | 0.76     |
| Voting Classifier        | 0.84     | 0.84      | 0.85      | 0.84     |
| **Bagging Classifier** ✅ | **0.90** | **0.895** | **0.90**  | **0.90** |
| AdaBoost                 | 0.79     | 0.79      | 0.79      | 0.79     |
| GradientBoost            | 0.81     | 0.81      | 0.81      | 0.81     |
| XGBoost                  | 0.86     | 0.86      | 0.87      | 0.855    |
| Random Forest            | 0.89     | 0.89      | 0.895     | 0.89     |
| Stacking Classifier      | 0.80     | 0.80      | 0.805     | 0.80     |
| Entity Embedding         | 0.78     | 0.78      | 0.785     | 0.785    |
| TabNet                   | 0.78     | 0.775     | 0.78      | 0.78     |
| Multi Layer Perceptron   | 0.77     | 0.775     | 0.79      | 0.775    |
| AutoInt                  | 0.79     | 0.785     | 0.80      | 0.785    |
| FT-Transformer           | 0.77     | 0.775     | 0.775     | 0.775    |
| Tab-Transformer          | 0.81     | 0.80      | 0.825     | 0.81     |

The experiment results show that the bagging classifier has the highest accuracy. Therefore, this app will use this model as the base model.

The model was initially saved in .pt (PyTorch) format, then converted to .onnx so it could be run in Android Studio.

Input Features : 
The application accepts input from users in the form of several categories that have been encoded as numbers: 
| Fitur            | Kategori                                       | Encoding |
| ---------------- | ---------------------------------------------- | -------- |
| Gender           | Male = 1, Female = 0                           |          |
| Partner          | Yes = 1, No = 0                                |          |
| Internet Service | Fiber optic = 1, DSL = 0                       |          |
| Online Security  | Yes = 1, No = 0                                |          |
| Tech Support     | Yes = 1, No = 0                                |          |
| Contract         | One year = 1, Monthly = 0                      |          |
| Payment Method   | Manual = 2, Credit Card = 1, Bank Transfer = 0 |          |
| Churn (Target)   | Yes = 1, No = 0                                |          |

Installation
1. Download Project File at : https://drive.google.com/file/d/1klBKay68T8VtrCouHy-zpq5WKI4N0FNX/view?usp=sharing 
2. Open Android Studio.
3. Ensure that the churn_bagging_proba.onnx model file is in the assets folder.
4. Run the application on an emulator or Android device.

Or you can try it out right away by downloading the demo app at the following link : https://drive.google.com/file/d/1SU4mfTdazlUWoLODI0-oY12_3BU2sByI/view?usp=sharing 

Tech Stack
- Python (scikit-learn, PyTorch) → Training & konversi model ke ONNX
- ONNX Runtime → Eksekusi model di Android
- Android Studio (Kotlin) → Aplikasi mobile
