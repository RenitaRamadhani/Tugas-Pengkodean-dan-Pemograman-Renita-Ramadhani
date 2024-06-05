# Nama : Renita Ramadhani #
# NIM : 12030122140270 #
# Kelas : Pengkodean dan Pemograman/D #

# Soal #
Buatlah sistem yang mencatat data penggajian dari setiap pekerja yang lengkap dan jelas, dan intrepetasi dari data tersebut !

# Cara Pengerjaan #
# Import pustaka yang dibutuhkan
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Langkah 1: Memuat Data
data = pd.read_csv('data.csv', sep=';')

# Langkah 2: Eksplorasi Data Awal

# Melihat beberapa baris pertama dari dataset
print("Beberapa baris pertama dari dataset:")
print(data.head())

# Informasi ringkas tentang dataset
print("\nInformasi dataset:")
print(data.info())

# Statistik deskriptif dari dataset
print("\nStatistik deskriptif dataset:")
print(data.describe())

# Mengecek missing values
print("\nMissing values:")
print(data.isnull().sum())

# Langkah 3: Visualisasi Dasar

# Histogram dari semua kolom numerik
print("\nVisualisasi histogram dari kolom numerik:")
data.hist(figsize=(10, 8))
plt.tight_layout()
plt.show()

# Visualisasi korelasi antar kolom numerik
print("\nVisualisasi heatmap korelasi:")
correlation_matrix = data.corr()
plt.figure(figsize=(10, 8))
plt.title('Correlation Matrix')
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', linewidths=0.5)
plt.show()

# Plot distribusi dari kolom tertentu (misal kolom 'age')
print("\nVisualisasi distribusi kolom 'age':")
plt.figure(figsize=(8, 6))
sns.histplot(data['age'], kde=True, bins=30)
plt.title('Distribution of Age')
plt.xlabel('Age')
plt.ylabel('Frequency')
plt.show()

# Scatter plot untuk dua kolom tertentu (misal 'age' dan 'salary')
print("\nScatter plot untuk 'age' dan 'salary':")
plt.figure(figsize=(8, 6))
plt.scatter(data['age'], data['salary'], alpha=0.5)
plt.title('Age vs. Salary')
plt.xlabel('Age')
plt.ylabel('Salary')
plt.show()

# Langkah 4: Mengatasi Missing Values (jika ada)

# Mengisi missing values dengan median (contoh)
print("\nMengisi missing values dengan median:")
data_filled = data.fillna(data.median())

print("Missing values setelah pengisian:")
print(data_filled.isnull().sum())

# Simpan dataset yang telah diisi missing values
data_filled.to_csv('data_filled.csv', index=False)

print("\nDataset yang telah diisi missing values disimpan sebagai 'data_filled.csv'")

# Langkah 5: Menyimpan perubahan ke file baru
data.to_csv('data_cleaned.csv', index=False)

print("\nDataset yang telah dibersihkan disimpan sebagai 'data_cleaned.csv'")

# Data #

# Hasil #

# Intrepetasi #


