# MediGuide

A Flask-based web application that helps users diagnose diseases and receive recommendations based on their symptoms. MediGuide leverages trained machine learning models and pre-loaded datasets to predict possible diseases and provide relevant guidance.

## Features
- Symptom-based disease prediction using an SVC machine learning model.
- Detailed descriptions of predicted diseases.
- Precautions, medications, diets, and workouts tailored to specific diseases.
- User-friendly web interface with routes for prediction, contact, developer information, blog, and more.

## Setup and Installation

### Prerequisites
- Python 3.x
- Flask
- NumPy
- Pandas
- Pickle
- Pre-trained SVC model (`svc.pkl`) and datasets placed in the local `models` and `datasets` folders respectively.

### Installation Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/Shreyash021104/MediGuide.git
   cd MediGuide
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

   > **Note:** Create a `requirements.txt` file if it does not exist:
   > ```
   > Flask
   > numpy
   > pandas
   > ```

3. Ensure that the following files exist in their respective directories:
   - `models/svc.pkl` - Pretrained Support Vector Classifier model.
   - `datasets/symtoms_df.csv` - Symptom dataset.
   - `datasets/precautions_df.csv` - Precautions dataset.
   - `datasets/workout_df.csv` - Workout recommendations dataset.
   - `datasets/description.csv` - Disease descriptions dataset.
   - `datasets/medications.csv` - Medications dataset.
   - `datasets/diets.csv` - Dietary recommendations dataset.

### Running the Application
1. Start the Flask development server:
   ```bash
   python main.py
   ```

2. Open your web browser and navigate to:
   ```
   http://127.0.0.1:5000
   ```

## How to Use the Application
1. Enter the symptoms in the input field separated by commas (e.g., `headache, fever, cough`).
2. Click "Predict" to receive the predicted disease and recommendations.
3. Navigate through other pages, such as "About", "Contact", "Developer", or "Blog", using the navigation bar.

## Project Structure
```
MediGuide/
├── datasets/            # CSV files containing symptoms, precautions, workouts, medications, etc.
├── models/              # Pre-trained model (svc.pkl).
├── templates/           # HTML templates for the web UI.
├── main.py              # Application entry point.
└── static/              # Static assets.
```

## Core Functions and Logic

### `helper(dis)`
- Retrieves detailed information about a specific disease, including:
  - Description
  - Precautions
  - Medications
  - Dietary recommendations
  - Suggested workouts

### `get_predicted_value(patient_symptoms)`
- Processes user-entered symptoms into a vector format.
- Predicts the disease using the pre-trained SVC model.

### Routes
- `/`: Main page for symptom input and disease prediction.
- `/about`: Information about the application.
- `/contact`: Contact page.
- `/developer`: Information about the developer.
- `/blog`: Blog section.

## Author
- **Shreyash021104**

## Contributing
Feel free to fork the repository and submit pull requests to suggest improvements or add new features.

## License
This project is licensed under the [MIT License](LICENSE).
