
import pandas as pd

# Load the CSV file into a DataFrame
df = pd.read_csv('data.csv')

# Display the DataFrame
print("Original DataFrame:")
print(df)
print()

# Filtering data based on conditions
# Filter out rows where Age is missing
df_filtered = df.dropna(subset=['Age'])

print("DataFrame after filtering out rows with missing Age:")
print(df_filtered)
print()

# Handling missing values
# Fill missing Age values with the mean Age
mean_age = df['Age'].mean()
df['Age'].fillna(mean_age, inplace=True)

# Fill missing Score values with the median Score
median_score = df['Score'].median()
df['Score'].fillna(median_score, inplace=True)

print("DataFrame after handling missing values:")
print(df)
print()

# Calculating summary statistics
print("Summary statistics:")
summary_stats = df.describe()
print(summary_stats)
