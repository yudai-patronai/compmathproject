# compmathproject
example repo for a solver project

В папке example представлен пример аппроксимации 1-мерной краевой задачи для уравненичя теплопроводности (диффузии). 
Файл .ipynb не имеет смысл запускать полностью - он носит скорее характер руководства. 

Структура файлов и папок примерно следующая :

- pde-solver-api/
    - main.py              # FastAPI server
    - schemas.py           # Pydantic models
    -  solvers/            # Numerical methods
         - heat_equation.py
    -  tests/              # Unit tests

Отрисовка в примере сделана с помощью библиотеки [plotly](https://plotly.com/python/animations/). 
Это быстрое решение, хотя более-менее стандартным и общепринятым является всё-таки использовние библиотеки [vtk](https://docs.vtk.org/en/latest/api/python.html) и отрисовщика [paraview](https://www.paraview.org/). По их использованию см [руководство](https://github.com/yudai-patronai/miniscience-4th-term/tree/master/2025/02_vtk)


Вызов солвера оформлен как приложение на сервере [uvicorn](https://www.uvicorn.org/#command-line-options)

все ваши солверы должны быть в одной папке solvers , по-хорошему, отрисовки должны быть в папке tests, несколько вариантов для разных входнях данных для каждого солвера. 

------------------

## Пример проектной работы - солвера по вычислительной математике.

Решалась задача Дирихле для 1-мерного уравнения теплопроводности.

$$
\partial_t u = \partial^2_{xx} u 
$$

с граничными условиями 

$$
u|_{t=0} = u_0,   
$$

$$
u|_{x=0} = u_L ,
$$

$$
u|_{x=X} = u_R
$$

Выполнили 
 - Вася Иванов (гр 102), Федя Федоров(гр 103), Мария Маринина(гр 104). 

# Зоны ответственности 

- **Вася Иванов** - явная 4-точечная схема

![Мультик](URL or file path)

- **Федя Федоров** - неявная 6-точечная схема

![Мультик](URL or file path)

- **Мария Маринина** - решение методом конечных элементов

![Мультик](URL or file path)


# Выводы.
Наиболее удобно использовать для решения задачи Дирихле для 1-мерного уравнения теплопроводности неявную схему типа Кранка-Николсона в силу ее абсолютной устойчивости, диагонального преобладания матрицы прогонки для неявной схемы. 
