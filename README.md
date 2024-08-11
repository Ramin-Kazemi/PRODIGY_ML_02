# Customer Segmentation Using K-Means Clustering

This project applies K-Means clustering to segment customers based on their purchase history using an e-commerce dataset. The goal is to identify distinct customer groups and analyze their purchasing behavior, which can be useful for targeted marketing and personalized services.

## Dataset

The dataset used for this project is the [E-Commerce Data](https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store) available on Kaggle. It contains detailed purchase records of customers, including transaction details, product information, and customer IDs.

### Key Columns in the Dataset:
- **InvoiceNo**: Unique identifier for each invoice/transaction.
- **StockCode**: Unique identifier for each product.
- **Description**: Description of the product.
- **Quantity**: Number of units purchased.
- **InvoiceDate**: Date and time when the invoice was generated.
- **UnitPrice**: Price per unit of the product.
- **CustomerID**: Unique identifier for each customer.
- **Country**: Country of the customer.

## Project Steps

### 1. Data Preprocessing
- **Handle Missing Values**: Rows with missing `CustomerID` or `Description` were dropped as these fields are essential for analysis.
- **Date Conversion**: The `InvoiceDate` column was converted to a datetime format.
- **Feature Engineering**: A new feature `TotalSpending` was created by multiplying `Quantity` and `UnitPrice`.

### 2. Feature Selection
Two key features were selected for clustering:
- **Frequency**: The number of unique transactions per customer.
- **TotalSpending**: The total amount spent by each customer.

### 3. Standardization
The features were standardized using `StandardScaler` to ensure that both features contribute equally to the distance calculations in the K-Means algorithm.

### 4. Optimal Number of Clusters
The Elbow method was used to determine the optimal number of clusters. The sum of squared distances (SSE) was plotted for different values of `k`, and the "elbow" point was identified.

### 5. K-Means Clustering
K-Means clustering was applied to segment the customers into distinct groups based on their purchasing behavior.

### 6. Visualization and Analysis
The resulting clusters were visualized using a scatter plot, and the cluster centers were analyzed to understand the characteristics of each customer segment.

## Results
The customers were successfully segmented into distinct groups, each representing a different purchasing behavior pattern. This segmentation can be used for targeted marketing strategies.

## How to Run

### Prerequisites
- Python 3.x
- Jupyter Notebook or any other IDE
- Required libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

### Instructions
1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/customer-segmentation-kmeans.git
    cd customer-segmentation-kmeans
    ```

2. Install the required libraries:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the notebook:
    ```bash
    jupyter notebook customer_segmentation_kmeans.ipynb
    ```

4. Follow the steps in the notebook to reproduce the analysis.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements
- Kaggle for providing the dataset.
- Scikit-learn for the K-Means algorithm implementation.

