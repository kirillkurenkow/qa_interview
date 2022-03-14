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
