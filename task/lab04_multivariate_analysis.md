# Laboratory Work 4 — Multivariate Data Analysis
# Лабораторная работа 4 — Многомерный анализ данных

---

## Описание лабораторной работы

### Название
**Лабораторная работа 4: Многомерный анализ данных для улучшения качества данных**

### Цель работы
Использовать методы многомерного анализа данных для повышения качества набора данных, изучая взаимодействия между переменными. Улучшения должны повысить точность прогноза модели машинного обучения.

### Краткое описание
В лабораторной работе рассматриваются:

- выявление линейных и нелинейных зависимостей между переменными;
- обнаружение мультиколлинеарности;
- снижение размерности данных с помощью PCA, t-SNE, UMAP;
- кластеризация и факторный анализ;
- генерация новых признаков и отбор признаков;
- использование Байесовских сетей для анализа зависимостей между переменными.

После многомерного анализа данные очищаются и преобразуются, а затем повторно обучается модель для оценки улучшений.

---

## Набор данных

Используется тот же набор данных, что и в предыдущем задании (Lab 3). Данные уже подверглись одномерному анализу и очистке. Цель — выявить многомерные зависимости и подготовить улучшенный набор данных для модели.

---

##  Задачи лабораторной работы

### 1. Первичный многомерный анализ

- **Корреляционная матрица и диаграммы рассеяния:** выявить линейные и нелинейные зависимости между переменными ($x_1, x_2, …, x_n$).
- **Выявление мультиколлинеарности:** использовать коэффициент инфляции дисперсии ($\text{VIF}$) для обнаружения избыточных переменных.

---

### 2. Продвинутые методы многомерного анализа

- **Анализ главных компонент (PCA):** уменьшение размерности при сильных корреляциях между предикторами.
- **t-SNE (t-распределение стохастического соседства):** визуализация высокоразмерных данных в 2D/3D пространстве для выявления кластеров.
- **UMAP (Универсальное приближение многообразия):** нелинейное уменьшение размерности с сохранением локальной структуры данных.
- **Факторный анализ:** выявление скрытых факторов, описывающих основные структуры данных.
- **Кластеризация:** использование $k$-means или иерархической кластеризации для выявления естественных группировок.

---

### 3. Дополнительные методы создания признаков

- **Генерация взаимодействий признаков:** создание новых признаков для моделирования нелинейных зависимостей.
- **Полиномиальные признаки:** расширение признаков для захвата сложных зависимостей.
- **Биннинг и дискретизация:** преобразование непрерывных переменных в категориальные.
- **Отбор признаков:** рекурсивное исключение признаков (RFE) или регуляризационные методы (например, Lasso).

---

### 4. Байесовские сети

- **Обучение структуры:** использование алгоритмов типа Hill-Climbing.
- **Условная независимость:** исследование зависимостей между переменными.
- **Применение:** использование сети для отбора признаков, генерации синтетических данных и балансировки классов.

---

### 5. Повторное построение модели

- Очистка, преобразование и сокращение набора данных после многомерного анализа.
- Обучение модели (регрессии или классификации) на обновленном наборе данных.
- Сравнение метрик модели до и после многомерного анализа.

---

## Отчёт

Отчёт должен содержать:

- Введение: описание набора данных, задачи и целей многомерного анализа.
- Многомерный анализ: описание методов и шагов обработки данных.
- Результаты: сравнение базовой модели, модели после одномерного и многомерного анализа.
- Заключение: выводы и влияние многомерного анализа на качество данных.

---

## Task Description (English Version)

### Title
**Laboratory Work 4: Multivariate Data Analysis for Data Quality Improvement**

### Objective
Use multivariate data analysis methods to improve data quality by studying interactions between variables. Improvements should increase the accuracy of a machine learning model.

### Description
Tasks include:

- identifying linear and nonlinear dependencies between variables;
- detecting multicollinearity;
- dimensionality reduction using PCA, t-SNE, UMAP;
- clustering and factor analysis;
- feature engineering and feature selection;
- Bayesian networks for dependency analysis.

After analysis, the data is cleaned, transformed, and the model is retrained to evaluate improvements.

---

##  Dataset

- Use the same dataset from Lab 3, already cleaned using univariate analysis.
- Goal: identify multivariate dependencies and prepare an improved dataset for modeling.

---

## Tasks

### 1. Initial Multivariate Analysis

- **Correlation matrix and scatter plots:** detect linear and nonlinear dependencies ($x_1, x_2, …, x_n$).
- **Multicollinearity detection:** use $\text{VIF}$ to identify redundant predictors.

---

### 2. Advanced Multivariate Methods

- **PCA:** reduce dimensionality with highly correlated predictors.
- **t-SNE:** visualize high-dimensional data in 2D/3D for cluster detection.
- **UMAP:** nonlinear dimensionality reduction preserving local structure.
- **Factor analysis:** identify latent factors representing data structure.
- **Clustering:** $k$-means or hierarchical clustering for natural groupings.

---

### 3. Feature Engineering

- **Interaction terms:** capture nonlinear dependencies.
- **Polynomial features:** extend predictors for complex dependencies.
- **Binning and discretization:** convert continuous variables to categorical.
- **Feature selection:** RFE or regularization methods (Lasso).

---

### 4. Bayesian Networks

- **Structure learning:** use algorithms like Hill-Climbing.
- **Conditional independence:** analyze variable dependencies.
- **Application:** feature selection, synthetic data generation, class balancing.

---

### 5. Model Retraining

- Clean, transform, and reduce dataset after multivariate analysis.
- Train regression or classification model on updated data.
- Compare metrics before and after multivariate analysis.

---

## Deliverables

- Jupyter Notebook with analysis code and model building.
- Plots, tables, and visualizations documenting the multivariate analysis.
- Report summarizing improvements and conclusions.
