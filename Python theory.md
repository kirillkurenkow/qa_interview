## Изменяемые и неизменяемые типы данных
#### Изменяемые (Mutable)
* `set` (Множество)
* `list` (Список)
* `dict` (Словарь)
#### Неизменяемые (Unmutable)
* `str` (Строка)
* `int`, `float` (Число)
* `bool` (Булевые переменные)
* `None`
* `tuple` (Кортеж)
* `Elliplis`

## Генераторы
#### Set (Множество)
```python
_ = {x for x in range(10)}  # {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
```
#### List (Список)
```python
_ = [x for x in range(10)]  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
_ = [x * y for y in range(2) for x in range(2)]  # [0, 0, 0, 1]
```
#### Dict (Словарь)
```python
_ = {str(x): x for x in range(5)}  # {'0': 0, '1': 1, '2': 2, '3': 3, '4': 4}
```
#### Generator (Генератор)
```python
_ = (x for x in range(10))  # <generator object <genexpr>>
```

## Декораторы
Декоратор — это паттерн проектирования (design pattern) в Python, а также функция второго уровня, \
то есть принимающая другие функции в качестве переменных и возвращающая их.

#### Пример простого декоратора
```python
def decorator(func):
    def wrapper(*args, **kwargs):
        return func(*args, **kwargs)
    
    return wrapper


@decorator
def some_func(*args, **kwargs):
    ...
```

#### Пример декоратора с параметрами
```python
def decorator_with_args(arg1, arg2):
    def decorator(func):
        def wrapper(*args, **kwargs):
            return func(*args, **kwargs)
        
        return wrapper
    
    return decorator


@decorator_with_args(arg1=1, arg2=2)
def some_func(*args, **kwargs):
    ...
```
