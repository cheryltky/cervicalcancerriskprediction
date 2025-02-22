# Cervical Cancer Risk Prediction

## Project Overview
This project implements a machine learning model to predict cervical cancer risk using patient medical data. Using XGBoost classification, the model achieves 95.8% accuracy in identifying potential cervical cancer cases based on various risk factors and medical test results.

## 🎯 Key Objectives
- Develop an accurate prediction model for cervical cancer risk assessment
- Analyze the importance of different medical indicators
- Provide insights into risk factor relationships

## 📊 Dataset
The dataset contains medical records from cervical cancer screening, including:

### Features:
- **Patient Demographics:** Age
- **Sexual Health History:** Number of partners, First intercourse age, Pregnancies
- **Risk Factors:** Smoking habits, Contraceptive use, STDs history
- **Medical Tests:** Hinselmann, Schiller, Cytology, Biopsy

### Target Variables:
Four different screening test results used for cervical cancer diagnosis

## 🛠️ Technical Implementation
### Technologies Used
- Python 3.7
- XGBoost 1.3.0
- Pandas, NumPy for data manipulation
- Seaborn, Matplotlib for visualization

### Model Performance
- Training Accuracy: 99.84%
- Testing Accuracy: 95.81%
- Precision (Class 1): 61%
- Recall (Class 1): 85%

## 📈 Key Findings
1. Model shows strong performance in identifying negative cases
2. Higher sensitivity (85% recall) for positive cases
3. Balanced accuracy across different test methods

## 🔄 Future Improvements
- [ ] Implement cross-validation
- [ ] Feature engineering for improved positive case detection
- [ ] Hyperparameter optimization
- [ ] Deploy model as web application

## 🙏 Acknowledgments
- Dataset source: UCI Machine Learning Repository
- Inspired by medical research in cervical cancer screening

## 📄 License
This project is licensed under the MIT License - see the LICENSE.md file for details
