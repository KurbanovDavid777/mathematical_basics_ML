# Laboratory Work 2 — Numerical Optimization Methods
# Лабораторная работа 2 — Использование численных методов в задачах оптимизации

---

## Описание лабораторной работы

### Название
**Лабораторная работа 2: Использование численных методов в задачах оптимизации**

### Цель работы
Познакомиться с современными численными методами оптимизации, реализовать алгоритмы BFGS и L-BFGS, а также применить конечно-разностные методы дифференцирования для решения прикладных задач оптимизации и обучения моделей машинного обучения.

### Краткое описание
В данной лабораторной работе рассматриваются задачи **безусловной оптимизации** с использованием численных методов. Основное внимание уделяется квазиньютоновским методам оптимизации — **BFGS** и **L-BFGS**, а также методам численного вычисления градиента на основе конечно-разностных схем.

Дополнительно проводится практическое применение реализованных алгоритмов оптимизации для обучения модели машинного обучения.

---

## Постановка задачи оптимизации

Рассматривается задача минимизации функции:

$$
f(x) \rightarrow \min, \quad x \in \mathbb{R}^n
$$

где целевая функция $f(x): \mathbb{R}^n \to \mathbb{R}$ является дважды дифференцируемой и выпуклой.

Искомое решение $x'$ удовлетворяет условию:

$$
f(x') \le f(x), \quad \forall x \in \mathbb{R}^n
$$

---

## Алгоритм BFGS

На $k$-й итерации используется квадратичная аппроксимация целевой функции:

$$
f(x_k + p) = f(x_k) + \nabla f(x_k)^T p + \frac{1}{2} p^T H(x_k) p
$$

Направление поиска:

$$
p_k = -H_k^{-1} \nabla f(x_k)
$$

Обновление точки:

$$
x_{k+1} = x_k + \alpha_k p_k
$$

где шаг $\alpha_k$ определяется с помощью **линейного поиска**, удовлетворяющего **условиям Вольфе**.

---

## Условия Вольфе

Параметр шага $\alpha_k$ должен удовлетворять:

$$
f(x_k + \alpha_k p_k) \le f(x_k) + c_1 \alpha_k \nabla f(x_k)^T p_k
$$

$$
\nabla f(x_k + \alpha_k p_k)^T p_k \ge c_2 \nabla f(x_k)^T p_k
$$

где $0 < c_1 < c_2 < 1$.

Для подбора шага используется алгоритм **line search** с процедурой `zoom`.

---

## Обновление приближённой матрицы Гессе

Приближённая обратная матрица Гессе обновляется по формуле:

$$
H_{k+1} = (I - \rho_k s_k y_k^T) H_k (I - \rho_k y_k s_k^T) + \rho_k s_k s_k^T
$$

где:

$$
s_k = x_{k+1} - x_k, \quad y_k = \nabla f(x_{k+1}) - \nabla f(x_k), \quad \rho_k = \frac{1}{y_k^T s_k}
$$

На первой итерации допускается инициализация $H_0 = I$.

---

## Метод L-BFGS

Метод **L-BFGS** является модификацией BFGS и позволяет существенно сократить потребление памяти за счёт хранения ограниченного числа векторов $s_k$ и $y_k$.

---

## Численное вычисление градиента

Для вычисления градиента используются конечно-разностные схемы:

**Односторонняя схема (1-й порядок):**

$$
\frac{\partial f}{\partial x_j} \approx \frac{f(x + h e_j) - f(x)}{h}
$$

**Центральная схема (2-й порядок):**

$$
\frac{\partial f}{\partial x_j} \approx \frac{f(x + h e_j) - f(x - h e_j)}{2h}
$$

---

## Задания

### 1. Исследование методов оптимизации

Рассматривается функция:

$$
f(x) = \frac{1}{2} \Big[ x_1^2 + \sum_{i=1}^{2} (x_i - x_{i+1})^2 + x_3^2 \Big] - x_1, \quad x \in \mathbb{R}^3
$$

Необходимо:

1. Показать, что методы **BFGS** и **L-BFGS** применимы к данной задаче.
2. Реализовать алгоритмы:
   - BFGS;
   - L-BFGS.

3. Для каждого алгоритма реализовать версии:
   - с аналитическим градиентом;
   - с численным градиентом (конечные разности).

   ❗ Использование `scipy.optimize` **запрещено**.

4. Реализовать различные способы инициализации матрицы Гессе:
   - единичная матрица;
   - приближение на основе конечных разностей.

5. Сравнить поведение алгоритмов по:
   - числу итераций;
   - скорости сходимости;
   - стабильности.

---

### 2. Практическое применение в машинном обучении

1. Использовать модель машинного обучения из **Лабораторной работы 1**.
2. Адаптировать обучение модели под численное вычисление градиента.
3. Реализовать алгоритм **Adam** с использованием конечно-разностных градиентов.
4. Обучить модель с использованием:
   - BFGS;
   - L-BFGS;
   - Adam (с разными гиперпараметрами).
5. Провести сравнительный анализ:
   - качества модели;
   - времени обучения;
   - устойчивости алгоритмов.

---

## Task Description (English Version)

### Title
**Laboratory Work 2: Numerical Methods for Optimization**

### Objective
To study modern numerical optimization methods, implement BFGS and L-BFGS algorithms, and apply finite-difference gradient approximations to solve optimization problems and train machine learning models.

### Description
This lab focuses on unconstrained optimization using numerical methods. The main emphasis is placed on quasi-Newton methods (BFGS and L-BFGS) and numerical differentiation techniques.

Additionally, the implemented optimization methods are applied to train a machine learning model.

---

## Tasks

### 1. Optimization Algorithms Study

Given the function:

$$
f(x) = \frac{1}{2} \Big[ x_1^2 + \sum_{i=1}^{2} (x_i - x_{i+1})^2 + x_3^2 \Big] - x_1
$$

1. Show that **BFGS** and **L-BFGS** are applicable to this problem.
2. Implement:
   - BFGS;
   - L-BFGS.

3. For each method, implement:
   - analytical gradient;
   - numerical gradient using finite differences.

   ❗ Usage of `scipy.optimize` is not allowed.

4. Implement different Hessian initializations.
5. Compare convergence behavior and performance.

---

### 2. Machine Learning Application

1. Use the machine learning model from **Laboratory Work 1**.
2. Adapt training to numerical gradient computation.
3. Implement **Adam** optimizer with finite-difference gradients.
4. Train the model using:
   - BFGS;
   - L-BFGS;
   - Adam.
5. Compare performance, training time, and stability.

---

## Expected Deliverables

- Jupyter Notebook with full implementations.
- Plots and convergence analysis.
- Conclusions on optimization methods efficiency.

