# Laboratory Work 1 — Matrix Decomposition Algorithms. PCA
# Лабораторная работа 1 — Алгоритмы разложения матриц. PCA

---

## Описание лабораторной работы

### Название
**Лабораторная работа 1: Алгоритмы разложения матриц. Метод главных компонент (PCA)**

### Цель работы
Изучить методы матричного разложения и их применение в анализе данных, включая метод главных компонент (PCA) и Kernel PCA для снижения размерности и решения задач классификации.

### Краткое описание
В работе рассматривается применение методов матричного разложения для анализа данных. Основной метод — PCA, который снижает размерность, проецируя данные в новое пространство, сохраняющее максимальную дисперсию.

Дополнительно предлагается реализовать **Kernel PCA** для классификации линейно-неразделимых данных.

---

## Теоретическая часть

Пусть дана матрица входных данных:

$$
X = 
\begin{pmatrix} 
x_1 \\ 
x_2 \\ 
\vdots \\ 
x_n 
\end{pmatrix}, \quad x_i \in \mathbb{R}^m
$$

Данные должны быть **центрированы по каждому признаку**.

Линейное преобразование данных:

$$
t_i = x_i W
$$

где:

- $W \in \mathbb{R}^{m \times s}$ — матрица главных компонент,  
- $s$ — число выбранных компонент.

Матрица $W$ формируется из собственных векторов матрицы ковариации $X^T X$. Вклад компоненты пропорционален соответствующему сингулярному числу.

---

## Сингулярное разложение

$$
X = U \Sigma V^T
$$

где:

- $U$ — матрица левых сингулярных векторов,  
- $\Sigma$ — диагональная матрица сингулярных чисел,  
- $V$ — матрица правых сингулярных векторов.

Сингулярные числа через собственные значения:

$$
\sigma_i = \sqrt{\lambda_i(XX^T)}
$$

---

## QR-алгоритм

Для вычисления собственных значений и векторов применяется **QR-алгоритм**:

$$
A = QR
$$

QR-разложение может быть реализовано через модифицированный метод ортогонализации Грама–Шмидта.

---

## Задания

### 1. Метод главных компонент (PCA)

1. Реализовать сингулярное разложение **без использования**:
   - `numpy.linalg.svd`
   - `numpy.linalg.eig`

   Рекомендуется использовать **QR-алгоритм**.

2. Выбрать ML-задачу на размеченной выборке:
   - не менее **5 признаков**;
   - модель: **искусственная нейронная сеть**.

3. Использовать SVD для:
   - получения главных компонент;
   - вычисления объясняемой дисперсии.

4. Определить число компонент:
   - визуализировать данные;
   - показать распределение целевой переменной в компонентном пространстве;
   - проанализировать смысл компонент (если применимо).

5. Оценить:
   - изменение качества модели;
   - время обучения после PCA.

6. *(Дополнительно)* Реализовать ускоренные методы SVD.

---

### 2. Kernel PCA

1. Выбрать линейно-неразделимый набор данных.
2. Реализовать ядровые матрицы:
   - полиномиальное ядро;
   - RBF-ядро;
   - сигмоидальное ядро.
3. Провести спектральное разложение ядровой матрицы.
4. Сравнить PCA и Kernel PCA:
   - визуализация проекций;
   - проверка линейной разделимости.
5. Оценить метрики классификации:
   - на исходных данных;
   - на данных после Kernel PCA.

---

## Task Description (English Version)

### Title
**Laboratory Work 1: Matrix Decomposition Algorithms. Principal Component Analysis (PCA)**

### Objective
Study matrix decomposition techniques and their application to data analysis, including PCA and Kernel PCA for dimensionality reduction and classification.

### Description
This lab focuses on applying matrix decomposition methods to analyze data. The core method is PCA, which reduces dimensionality by projecting data into a new coordinate system that preserves maximum variance.

An additional task involves implementing **Kernel PCA** for non-linearly separable datasets.

---

## Tasks

### 1. Principal Component Analysis (PCA)

1. Implement Singular Value Decomposition **from scratch**, without using:
   - `numpy.linalg.svd`
   - `numpy.linalg.eig`

   The **QR algorithm** is recommended.

2. Select a labeled ML dataset:
   - at least **5 features**;
   - model: **artificial neural network**.

3. Use the implemented SVD to:
   - compute principal components;
   - calculate explained variance.

4. Determine an appropriate number of components:
   - visualize transformed data;
   - analyze target distribution in component space;
   - interpret components if possible.

5. Evaluate:
   - model performance changes;
   - training time differences after PCA.

6. *(Optional)* Implement computationally efficient SVD variants.

---

### 2. Kernel PCA

1. Select a non-linearly separable dataset.
2. Implement kernel matrices:
   - polynomial kernel;
   - RBF kernel;
   - sigmoid kernel.
3. Perform spectral decomposition of the kernel matrix.
4. Compare PCA and Kernel PCA:
   - projection visualization;
   - linear separability analysis.
5. Evaluate classification metrics:
   - on original data;
   - on Kernel PCA-transformed data.

---

## Expected Deliverables

- Jupyter Notebook with implementation.  
- Visualizations and explanations.  
- Conclusions on PCA and Kernel PCA effectiveness.
