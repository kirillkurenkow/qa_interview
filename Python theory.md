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

## Pytest
### Фикстуры (Fixtures)
Тестовые фикстуры инициализируют тестовые функции. Они обеспечивают надежность тестов, согласованность и повторяемость их результатов. \
При инициализации можно настраивать сервисы, состояния, переменные окружения. \
Доступ к ним осуществляется через аргументы тестовых функций; для каждой фикстуры, используемой тестовой функцией, \
в самой функции, как правило, существует соответствующий аргумент, имя которого совпадает с наименованием фикстуры.

#### Области действия фикстур (Scope)
##### function
Выполняется один раз для каждой функции теста. Часть setup запускается перед каждым тестом с помощью fixture. \
Часть teardown запускается после каждого теста с использованием fixture. \
Это область используемая по умолчанию, если параметр scope не указан.

##### class
Выполняется один раз для каждого тестового класса, независимо от количества тестовых методов в классе.

##### module
Выполняется один раз для каждого модуля, независимо от того, сколько тестовых функций или методов или других фикстур при использовании модуля.

##### session
Выполняется один раз за сеанс. Все методы и функции тестирования, использующие фикстуру области сеанса, используют один вызов setup и teardown.

#### Примеры фикстур
```python
from pytest import fixture


@fixture(scope='function')
def some_fixture():
    # setup
    yield 
    # teardown
```
```python
from pytest import fixture


class DataBase:
    ...


@fixture(scope='session')
def database():
    database = DataBase()
    yield database
```