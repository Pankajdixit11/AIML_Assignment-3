# Salary Prediction using Polynomial Regression

## Objective
The objective of this project is to develop a Polynomial Regression model to predict employee salaries based on their position level within a company. Since the relationship between position level and salary is inherently non-linear, this project demonstrates how Polynomial Regression can effectively capture complex patterns and provide accurate salary predictions across all organizational levels.

## Dataset Link
**Source:** [Position Salaries Dataset](https://www.kaggle.com/datasets/akram24/position-salaries)  
**Dataset Description:** The dataset contains 10 records with information about position levels and corresponding salaries. It includes three columns:
- Position: Job title/position name
- Level: Position level (1-10, with 10 being the highest)
- Salary: Annual salary in USD

## Libraries Used
The following Python libraries were used in this project:

| Library | Version | Purpose |
|---------|---------|---------|
| Pandas | 1.5.0+ | Data loading, manipulation, and analysis |
| NumPy | 1.23.0+ | Numerical computations and array operations |
| Matplotlib | 3.6.0+ | Data visualization and plotting |
| Scikit-learn | 1.2.0+ | Machine learning models and evaluation metrics |

### Detailed Library Usage:
- **Pandas**: Loading the dataset, displaying summary statistics, data preprocessing
- **NumPy**: Creating grid values for visualization and mathematical operations
- **Matplotlib**: Creating scatter plots and regression curves for visual analysis
- **Scikit-learn**:
  - `train_test_split`: Splitting data into training and test sets
  - `PolynomialFeatures`: Generating polynomial features for non-linear modeling
  - `LinearRegression`: Building the regression model
  - `mean_absolute_error`, `mean_squared_error`, `r2_score`: Model evaluation

## Methodology

### 1. Data Understanding
- Loaded the Position Salaries dataset using Pandas
- Identified **Level** as the input feature (independent variable) and **Salary** as the target variable (dependent variable)
- Performed exploratory data analysis to understand data distribution and relationships

### 2. Data Preprocessing
- Checked for missing values (none found)
- Selected appropriate feature (`Level`) and target (`Salary`)
- Split the dataset into 80% training and 20% testing sets using `train_test_split`

### 3. Model Development
- **Polynomial Feature Transformation**: Transformed the input feature using Polynomial Features with Degree = 3
- **Model Training**: Trained a Linear Regression model on the polynomial-transformed features
- **Prediction**: Generated salary predictions for the test dataset

### 4. Model Evaluation
The model was evaluated using the following metrics:
- **Mean Absolute Error (MAE)**: Measures average absolute prediction error
- **Mean Squared Error (MSE)**: Penalizes larger errors more heavily
- **R² Score**: Indicates the proportion of variance explained by the model

### 5. Visualization
- Created a scatter plot of the original data points
- Plotted the Polynomial Regression curve to visualize the non-linear relationship

## Results

### Model Performance Metrics
| Metric | Value |
|--------|-------|
| R² Score | ~0.99 (near perfect fit) |
| Mean Absolute Error (MAE) | Very low |
| Mean Squared Error (MSE) | Very low |

### Comparison with Linear Regression
| Model | R² Score | MAE |
|-------|----------|-----|
| Linear Regression | Lower | Higher |
| Polynomial Regression (Degree 3) | Higher (~0.99) | Lower |

![Polynomial Regression Curve](https://github.com/Pankajdixit11/AIML_Assignment3/blob/82c8075e0f54b483ecb59df415c9be6f4e2e789e/Polynomial%20Regression%20Curve.png)

### Key Observations
1. **Strong Non-linear Relationship**: The data shows a clear non-linear pattern, with salaries increasing at an accelerating rate at higher position levels.
2. **Excellent Model Fit**: The Polynomial Regression model explains approximately 99% of the variance in salaries, indicating an excellent fit.
3. **Superior Performance**: Polynomial Regression significantly outperforms Linear Regression, demonstrating the importance of capturing non-linear patterns.

### Visualization
The regression curve clearly shows:
- Gradual salary increase at lower levels (1-5)
- Accelerated salary growth at mid to senior levels (6-8)
- Exponential-like increase at executive levels (9-10)

## Conclusion

This project successfully developed a Polynomial Regression model (Degree 3) to predict employee salaries based on position level. The key finding is that the relationship between position level and salary is strongly non-linear, with salaries escalating rapidly at higher organizational levels.

**Comparison with Linear Regression:**
While Linear Regression assumes a constant rate of salary increase per level, Polynomial Regression captures the complex, curved relationship in the data. The Polynomial Regression model achieved an R² score of approximately 0.99, significantly outperforming Linear Regression, which could not accurately model the exponential growth pattern at executive levels.

**Advantage of Polynomial Regression:**
The primary advantage of Polynomial Regression for this dataset is its flexibility in modeling the escalating salary structure. This enables companies to:
- Make more accurate salary predictions across all position levels
- Better plan compensation for executive roles where salaries increase rapidly
- Make informed budget allocation decisions
- Develop strategic workforce planning initiatives

The success of this model demonstrates that for non-linear relationships in organizational data, Polynomial Regression provides superior predictive accuracy compared to simpler linear models.

## How to Run the Code

### Prerequisites
```bash
pip install pandas numpy matplotlib scikit-learn
