# 🎾 Naïve Bayes Classifier: Play Tennis Dataset

This project demonstrates the implementation of a **Naïve Bayes classifier** using a simple categorical dataset (`Play Tennis`) to predict whether to play tennis based on weather conditions.

---

## 🧠 Algorithm

The algorithm used is **Categorical Naïve Bayes** from `scikit-learn`, suitable for handling categorical features such as:

- Outlook (`Sunny`, `Overcast`, `Rain`)
- Temperature (`Hot`, `Mild`, `Cool`)
- Humidity (`High`, `Normal`)
- Windy (`True`, `False`)

---

## 📁 Dataset

- Filename: `Play_tennis.csv`
- Location: `C:\Users\SARTHAK\Desktop\Naive Bayes\Play_tennis.csv`
- Columns:
  - `outlook`
  - `temperature`
  - `humidity`
  - `windy`
  - `play` (target)

Ensure that all values are categorical and there are no missing entries.

---

## 🛠️ How It Works

1. Loads the CSV file.
2. Cleans and normalizes column names.
3. Encodes all categorical features using `LabelEncoder`.
4. Splits the data into training and testing sets (80/20).
5. Trains a `CategoricalNB` model.
6. Outputs:
   - Accuracy
   - Classification report
   - Confusion matrix (visual)
7. Predicts a user-defined sample input.

---

## 📈 Output Example

- **Accuracy**: 100.0%
- **Confusion Matrix**:
[[1 0]
[0 2]]

- **Prediction** for input `['sunny', 'cool', 'high', False]`: `No`

---

## 🔮 Sample Prediction Code

```python
new_sample = pd.DataFrame([['sunny', 'cool', 'high', False]],
                        columns=['outlook', 'temperature', 'humidity', 'windy'])

# Encode and predict
for col in new_sample.columns:
  new_sample[col] = label_encoders[col].transform(new_sample[col])
prediction = model.predict(new_sample)
print(label_encoders['play'].inverse_transform(prediction)[0])
