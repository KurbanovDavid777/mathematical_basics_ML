# Laboratory Work 3 — Univariate Data Analysis
# Лабораторная работа 3 — Одномерный анализ данных

---

## Описание лабораторной работы

### Название
**Лабораторная работа 3: Одномерный анализ данных для улучшения качества данных**

### Цель работы
Применить методы одномерного анализа данных для выявления проблем в наборе данных и улучшения его качества. Данные улучшения должны привести к более точной работе модели машинного обучения без усложнения самой модели.

### Краткое описание
В этой лабораторной работе анализируются отдельные переменные в наборе данных для задач регрессии или классификации. Основное внимание уделяется:

- выявлению пропущенных значений;
- обнаружению выбросов и ошибок ввода;
- исправлению скошенности распределений;
- нормализации и масштабированию переменных.

Эти операции улучшают качество данных, что напрямую повышает эффективность моделей машинного обучения.

---

## Набор данных

Набор данных должен содержать:

- **Зависимая переменная ($y$)** — целевая переменная для прогноза;
- **Не менее 5 независимых переменных ($x_1, x_2, …$)** — предикторы, как непрерывные, так и дискретные;
- Недостатки данных:
  - пропущенные значения;
  - выбросы;
  - скошенные распределения;
  - шум и ошибки ввода.

---

## Задачи лабораторной работы

### 1. Первоначальная модель

- Обучить простую линейную модель (регрессия или логистическая регрессия) на исходных данных «как есть».
- Оценить показатели эффективности:
  - $R^2$, RMSE для регрессии;
  - F1, ROC-AUC для классификации.

---

### 2. Одномерный анализ данных

Для каждой переменной:

1. **Описательная статистика**  
   Рассчитать и интерпретировать: среднее, медиану, стандартное отклонение, диапазон, квартили, асимметрию и эксцесс.

2. **Визуализация данных**  
   Построить гистограммы, boxplot, графики плотности для выявления проблем.

3. **Обработка пропущенных значений**  
   Определить пропуски, выбрать стратегию (удаление, заполнение медианой/средним) и обосновать выбор.

4. **Обнаружение и устранение выбросов**  
   Использовать IQR или Z-score, определить стратегию обработки (удаление, трансформация).

5. **Преобразование переменных**  
   Если есть скошенность или ненормальность — применять логарифм, квадратный корень или Box-Cox.

6. **Масштабирование переменных**  
   Стандартизировать или нормализовать переменные с широким диапазоном значений.

7. **Удаление шума**  
   Удалить очевидные ошибки ввода и шум, используя одномерные распределения.

---

### 3. Повторное обучение модели

- Обучить ту же модель на очищенных и преобразованных данных.
- Сравнить показатели с исходными:
  - $R^2$, RMSE, F1, ROC-AUC.
- Проанализировать влияние одномерного анализа на эффективность модели.

---

## Отчёт

Отчёт должен включать:

- Введение: описание набора данных и задачи.
- Одномерный анализ: подробное описание очистки данных и визуализации.
- Результаты: базовая и улучшенная модель, сравнение метрик.
- Заключение: выводы и влияние одномерного анализа на эффективность модели.

---

## Task Description (English Version)

### Title
**Laboratory Work 3: Univariate Data Analysis for Data Quality Improvement**

### Objective
Apply univariate data analysis techniques to detect issues in a dataset and improve its quality. Improved data should lead to better performance of a machine learning model without increasing model complexity.

### Description
Focus on individual variables for regression or classification tasks. Key tasks include:

- handling missing values;
- detecting outliers and input errors;
- correcting skewed distributions;
- normalizing and scaling variables.

These operations improve data quality and enhance model performance.

---

## Dataset Requirements

- **Target variable ($y$)** — variable to predict.
- **At least 5 predictor variables ($x_1, x_2, …$)**, continuous or discrete.
- Dataset should include:
  - missing values;
  - outliers;
  - skewed distributions;
  - noise and input errors.

---

## Tasks

### 1. Initial Model

- Train a simple linear model (regression or logistic regression) on raw data.
- Evaluate metrics:
  - $R^2$, RMSE for regression;
  - F1, ROC-AUC for classification.

---

### 2. Univariate Data Analysis

For each variable:

1. **Descriptive statistics**  
   Calculate mean, median, standard deviation, range, quartiles, skewness, and kurtosis.

2. **Data visualization**  
   Use histograms, boxplots, density plots to detect issues.

3. **Handling missing values**  
   Identify missing values, choose a strategy (removal, mean/median imputation) and justify.

4. **Outlier detection and treatment**  
   Use IQR or Z-score, choose treatment (removal, transformation).

5. **Variable transformation**  
   Apply log, square root, or Box-Cox for skewed or non-normal distributions.

6. **Scaling variables**  
   Standardize or normalize variables with wide ranges.

7. **Noise removal**  
   Remove obvious input errors and noise using univariate distributions.

---

### 3. Retraining the Model

- Retrain the same model on cleaned and transformed data.
- Compare metrics with the initial model:
  - $R^2$, RMSE, F1, ROC-AUC.
- Analyze the impact of univariate analysis on model performance.

---

## Deliverables

- Jupyter Notebook with full analysis and model training.
- Plots and tables documenting univariate analysis.
- Report summarizing improvements and conclusions.
