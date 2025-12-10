import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the updated dataset
df = pd.read_csv('Housing.csv')

# Q1: Average, minimum, and maximum house prices
print("Average price:", df['price'].mean())
print("Minimum price:", df['price'].min())
print("Maximum price:", df['price'].max())

# Q2: Correlation with bedrooms, bathrooms; scatter plots
print("Price ↔ Bedrooms correlation:", df['price'].corr(df['bedrooms']))
print("Price ↔ Bathrooms correlation:", df['price'].corr(df['bathrooms']))

plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.scatter(df['bedrooms'], df['price'])
plt.xlabel('Number of Bedrooms')
plt.ylabel('House Price')
plt.title('House Price vs Number of Bedrooms')

plt.subplot(1, 2, 2)
plt.scatter(df['bathrooms'], df['price'])
plt.xlabel('Number of Bathrooms')
plt.ylabel('House Price')
plt.title('House Price vs Number of Bathrooms')
plt.tight_layout()
plt.show()

# Q3: Average price by district/region
print(df.groupby('district')['price'].mean())
plt.bar(df['district'].unique(), df.groupby('district')['price'].mean()[df['district'].unique()])
plt.xlabel('District/Region')
plt.ylabel('Average House Price')
plt.title('Average House Price by District/Region')
plt.show()

# Q4: Relationship between size (area) and price
print("Price ↔ Area correlation:", df['price'].corr(df['area']))
plt.scatter(df['area'], df['price'])
plt.xlabel('Area (square feet)')
plt.ylabel('House Price')
plt.title('House Price vs Area')
plt.show()

# Q5: Outliers in price (boxplot and filtering)
sns.boxplot(x=df['price'])
plt.title('House Price Outliers')
plt.xlabel('House Price')
plt.show()

outliers = df[np.abs(df['price'] - df['price'].mean()) > (3 * df['price'].std())]
print('Number of outliers:', len(outliers))
print('Outlier example prices:\n', outliers.head(3)['price'])
