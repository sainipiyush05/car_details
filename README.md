## Car Details

# 🚗 Car Price Prediction using Machine Learning

This project uses machine learning models to predict the **selling price of used cars** based on features such as year, kilometers driven, fuel type, transmission, ownership history, and car brand.

---

## 📂 Dataset

The dataset was sourced from **Car Dekho**, containing information like:
- `name`: Full car name
- `year`: Year of manufacture
- `km_driven`: Kilometers driven
- `fuel`: Fuel type (Petrol, Diesel, etc.)
- `seller_type`: Individual, Dealer, etc.
- `transmission`: Manual or Automatic
- `owner`: Ownership history
- `selling_price`: Target variable (price in ₹)

---

## 🧠 Features Used

After preprocessing, the following features were used:
- `year`
- `km_driven`
- `fuel`
- `seller_type`
- `transmission`
- `owner`
- `brand` *(extracted from the car name)*

---

## 🔧 Preprocessing

- Extracted car brand from the `name` column.
- Dropped the full `name` as it's too specific.
- Used `OneHotEncoder` with `handle_unknown='ignore'` for categorical features.
- Used a `ColumnTransformer` and `Pipeline` for clean preprocessing and modeling.

---

## 🏁 Models Compared

1. **Linear Regression**
2. **Random Forest Regressor**
3. **Gradient Boosting Regressor**

Evaluation metrics:
- **RMSE** (Root Mean Squared Error)
- **R² Score** (Coefficient of Determination)

---

## 🏆 Best Model: Random Forest Regressor

### ✅ Hyperparameter Tuning
Tuned using `GridSearchCV` with 5-fold cross-validation.

Best parameters found:
- `n_estimators`: 200
- `max_depth`: 20
- `min_samples_split`: 2

### 📊 Performance (on test data):
- **RMSE**: ₹X,XXX.XX *(updated dynamically)*
- **R² Score**: 0.XXXX

---

## 🔮 Prediction Example

```python
new_data = pd.DataFrame([{
    'year': 2020,
    'km_driven': 15000,
    'fuel': 'Petrol',
    'seller_type': 'Individual',
    'transmission': 'Manual',
    'owner': 'First Owner',
    'brand': 'Hyundai'
}])

predicted_price = model.predict(new_data)


📦 Dependencies
pandas

numpy

scikit-learn

Install via pip:

bash
Copy
Edit
pip install pandas numpy scikit-learn
📁 Project Structure
bash
Copy
Edit
.
├── CAR DETAILS FROM CAR DEKHO.csv   # Dataset
├── model_training.py                # Main model training and prediction script
├── README.md                        # Documentation
📌 Key Takeaways
Tree-based models like Random Forest performed best.

Using Pipeline and ColumnTransformer ensures clean and modular code.

Robust handling of unseen categories with handle_unknown='ignore'.

💡 Future Improvements
Add more granular info like engine, seats, torque if available.

Use deep learning or ensemble stacking for better performance.

Deploy the model using Flask or Streamlit.

👨‍💻 Author
Piyush Saini
B.Tech CSE @ SRM IST | AI/ML Enthusiast | LinkedIn

