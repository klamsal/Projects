```

# Import necessary libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
df = pd.read_csv("supermarket_sales.csv")

# Display the first few rows
df.head()

```


```

# Overview of the dataset
df.info()
df.describe()
# Check for missing values
df.isnull().sum()

```


```

# Histogram of total sales
plt.figure(figsize=(8, 5))
sns.histplot(df['Total'], kde=True)
plt.title('Distribution of Total Sales')
plt.xlabel('Total Sales')
plt.ylabel('Frequency')
plt.show()

```


```

# Bar plot: Average Total Sales by Gender
plt.figure(figsize=(8, 5))
sns.barplot(data=df, x='Gender', y='Total', ci=None)
plt.title('Average Total Sales by Gender')
plt.xlabel('Gender')
plt.ylabel('Average Total Sales')
plt.show()

```


```

# Pie chart for payment method distribution
payment_counts = df['Payment'].value_counts()
payment_counts.plot.pie(autopct='%1.1f%%', figsize=(8, 5))
plt.title('Payment Method Distribution')
plt.ylabel('')
plt.show()

```


```

# Heatmap to visualize correlations
plt.figure(figsize=(8, 5))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm', fmt=".2f")
plt.title('Correlation Heatmap')
plt.show()

```
