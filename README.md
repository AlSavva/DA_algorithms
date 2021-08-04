# DA_algorithms

# Методички и практические задания по курсу "Алгоритмы анализа данных"  

## Лекция1. Алгоритм линейной регрессии. Градиентный спуск.  

### Практическое задание к лекции 1.  

---

**1. Подберите скорость обучения(<img src="https://render.githubusercontent.com/render/math?math=%24%5Calpha%24">) и количество итераций:**  

```
n = X.shape[1]  
alpha = 1e-04

W = np.array([1, 0.5])   
W, alpha   
```
```
for i in range(1500):  
    y_pred = W @ X  
    err = calc_mse(y, y_pred)  
    for ii in range(W.shape[0]):  
        W[ii] -= alpha * (1 / n * 2 * np.sum(X[ii] * (y_pred - y)))  
    if i % 100 == 0:  
        print(i, W, err)  
```
**2\*. В этом коде мы избавляемся от итераций по весам, но тут есть ошибка, исправьте ее:**  

```
for i in range(287):
    y_pred = np.dot(W, X)
    err = calc_mse(y, y_pred)
    # for ii in range(W.shape[0]):
    # W[ii] -= alpha * (1/n * 2 * np.sum(X[ii] * (y_pred - y)))
    W -= (alpha * (1 / n * 2 * np.sum(X * (y_pred - y))))
    if i % 10 == 0:
        print(i, W, err)
```
