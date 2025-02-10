# BigData
# Final Project: Big Data Processing

## 📌 Overview

This project is the final assignment for the **Big Data Processing** course, focusing on applying **PySpark** for large-scale data processing. The project includes implementing dimensionality reduction using **Singular Value Decomposition (SVD)** and other data transformation techniques.

## ⚙️ Setup and Installation

### 1️⃣ Install Java & PySpark

```sh
!apt-get install openjdk-8-jdk-headless -qq > /dev/null
!wget -q http://archive.apache.org/dist/spark/spark-3.1.1/spark-3.1.1-bin-hadoop3.2.tgz
!tar xf spark-3.1.1-bin-hadoop3.2.tgz
!pip install -q findspark
```

### 2️⃣ Set Environment Variables

```python
import os
os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-8-openjdk-amd64"
os.environ["SPARK_HOME"] = "/content/spark-3.1.1-bin-hadoop3.2"
import findspark
findspark.init()
```

### 3️⃣ Run PySpark

```python
from pyspark import SparkContext
from pyspark.sql import SQLContext
sc = SparkContext("local", "FinalProject")
sqlc = SQLContext(sc)
```

## 🚀 Key Features

- **Data Loading & Preprocessing**: Reads large-scale datasets efficiently.
- **Dimensionality Reduction (SVD)**: Reduces feature space to improve performance.
- **PySpark Integration**: Leverages distributed computing for scalability.
- **Visualization**: Uses Matplotlib for data visualization.

## 📊 Example: Dimensionality Reduction using SVD

```python
import numpy as np
data = sc.textFile('/content/oxford_pet3_train.csv')
data_reshape = data.map(lambda x: x.split(','))\
              .map(lambda x: (x[0], x[1], np.array(x[2:], dtype=int).reshape(128,128,3)))
```

## 📌 Contributors

- **Instructor**: Th.S. Nguyễn Thành An
- **Academic Year**: 2022-2023, Semester 1

## 📝 License

This project is for educational purposes only.

## 📬 Contact

For any inquiries, please reach out to [beaufull2002@gmail.com].

