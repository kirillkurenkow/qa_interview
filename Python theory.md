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

## Классы (Classes)
### Модификаторы доступа
##### Виды модификаторов
* Public (публичные) - методы доступны везде
* Protected (защищенные) - внутри класса и в дочерних классах
* Private (приватные) - методы доступны только внутри класса

```python
class SomeClass:
    def public_method(self):
        ...
    
    def _secured_method(self):
        ...

    def __private_method(self):
        ...
```

### Magic методы
#### Метод `__new__()`
Вызывается перед `__init__`. 

Возвращает новый объект, который, в последствии, инициализируется с помощью `__init__`.

#### Метод `__init__()`
Вызывается методом `__new__`. Инициализирует объект.

Возвращает инициализированный объект класса.

#### Метод `__del__()`
Метод для удаления объекта класса.

#### Метод `__str__()` 
Вызывается при попытке привести объект класса к типу `str`. 

Возвращает строковое представление объекта.

#### Метод `__repr__()`
Вызывается при передаче объекта класса функции `repr()`.

Возвращает машиночитаемое представление объекта.

#### Унарные методы
```
__pos__()       +some_object
__neg__()       -some_object
__abs__()       abs(some_object)
__invert__()    ~some_object
__round__()     round(some_object)
__floor__()     math.floor(some_object)    
__ceil__()      math.ceil(some_object)
__trunc__()     math.trunc(some_object)
```

#### Математические и логические методы
Вызываются при каких-либо логических/математических операциях с объектом класса.

Список методов:
```
 __add__()       +
 
 __sub__()       -
 
 __mul__()       *
 
 __floordiv__()  //
 
 __truediv__()   /
 
 __mod__()       %
 
 __pow__()       **
 
 __lt__()        <
 
 __le__()        <=
 
 __eq__()        ==
 
 __ne__()        !=
 
 __ge__()        >=
```

#### Методы атрибутов
* `__getattr__()` - Получение атрибута
* `__setattr__()` - Присвоение атрибута
* `__delattr__()` - Удаление атрибута


### Статические методы
Статические методы объявляются при помощи декоратора `staticmethod`:
```python
class SomeClass:
    @staticmethod
    def static_method(): ...
```
Статические методы могут вызываться без инициализации объекта класса и им не нужен аргумент `self`.

### Свойства (Property)
Свойства в классах позволяют получить атрибут, значение которого вычисляется динамически.

Примеры объявления свойств:
```python
class SomeClass:
    @property
    def some_property(self): 
        return ...
```
```python
class SomeClass:
    @property
    def some_property(self):
        return ...

    @some_property.setter
    def some_property(self, value):
        ...
    
    @some_property.deleter
    def some_property(self):
        ...
```

### Наследование
Наследование подразумевает то, что дочерний класс содержит все атрибуты родительского класса, \
при этом некоторые из них могут быть переопределены или добавлены в дочернем.

Изначально все классы наследуют класс `object`.\
Это значит, что записи
```python
class SomeClass: ...
```
и
```python
class SomeClass(object): ...
```
равнозначны.

Пример наследования:
```python
class Car: ...
class Truck(Car): ...
```

#### Множественное наследование 
Пример:
```python
class Car: ...
class Boat: ...
class Amphibian(Car, Boat): ...
```

#### Порядок разрешения методов (MRO)
В Python3 для определения порядка используется алгоритм поиска в ширину, \
то есть сначала интерпретатор будет искать метод `hi` в классе `B`, если его там нет - в классе `С`, потом `A`:
```python
class A:
    def hi(self): ...
    
    
class B(A):
    def hi(self): ...
 
    
class C(A):
    def hi(self): ...
 

class D(B, C): ...
```

Порядок, в котором будут наследоваться классы можно увидеть с помощью функции `mro()`.

#### super()
При помощи функции `super()` можно обратиться к экземпляру родительского класса

Пример:
```python
class Car:
    def __init__(self, wheels_count: int = 4):
        self.wheels = wheels_count

        
class Truck(Car):
    def __init__(self):
        super().__init__(wheels_count=6)
```

## Асинхронный код
<b>Python Global Interpreter Lock (GIL)</b> — это своеобразная блокировка, позволяющая только одному потоку управлять интерпретатором Python. Это означает, что в любой момент времени будет выполняться только один конкретный поток.

#### Когда использовать multiprocessing, asyncio или threading
1. Используйте многопроцессорность (multiprocessing), когда вам нужно выполнить много тяжелых вычислений, и вы можете их разделить.
2. Используйте asyncio или многопоточность(threading), когда вы выполняете операции ввода-вывода - общение с внешними ресурсами или чтение/запись из/в файлы.
3. Многопроцессорность и asyncio можно использовать вместе, но хорошее практическое правило состоит в том, чтобы разветвлять процесс перед потоком/использованием asyncio, а не наоборот - потоки относительно дешевы по сравнению с процессами.

### Multiprocessing
Пример:
```python
import multiprocessing


def some_func(): ...


processes = []
for _ in range(5):
    process = multiprocessing.Process(
        target=some_func,
        args=(),
        kwargs={},
    )
    process.start()
    processes.append(process)

for process in processes:
    process.join()
```

### Threading
<b>Поток</b> - это способ позволить вашему компьютеру разбить отдельный процесс/программу на множество легковесных частей, которые выполняются параллельно.

Потоки в Python являются конкурентными, но не параллельными из-за GIL.

Пример:
```python
import threading


def some_func(): ...


threads = []
for _ in range(5):
    thread = threading.Thread(
        target=some_func,
        args=[],
        kwargs={},
    )
    thread.start()
    threads.append(thread)

for thread in threads:
    thread.join()
```

### AsyncIO
Пример:
```python
import asyncio
import aiofile


async def create_file(filename: str):
    async with aiofile.async_open(filename, mode='w') as file:
        await file.write(filename * 30)


async def main():
    tasks = []
    for i in range(5):
        tasks.append(create_file(filename=f'test{i}.txt'))
    await asyncio.gather(*tasks)


asyncio.run(main())
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

### Marks
Чтобы использовать кастомные теги надо добавить их в `pytest.ini`
```ini
[pytest]
markers=
    mark1: mark for tests ...
    mark2: mark for other tests ...
```
```python
import pytest


@pytest.mark.mark1
def some_test(): ...
```
Чтобы запустить тесты с определенными тегами нужно использовать аргумент `-m`:
```shell
pytest -m mark1
```
```shell
pytest -m "mark1 AND mark2"
```
```shell
pytest -m "not mark1"
```
#### mark.parametrize
Используется для параметризации тестов
```python
import pytest


@pytest.mark.parametrize('param1, param2', [
    (1, 1),
    (2, 2),
    (3, 3)
])
def test_1(param1, param2):
    ...


@pytest.mark.parametrize('param', list(range(10)))
def test_2(param):
    ...


@pytest.mark.parametrize('param1', [1, 2, 3])
@pytest.mark.parametrize('param2', [1, 2, 3])
def test_3(param1, param2):
    ...
```

#### mark.skip
Используется, чтобы пропускать (не запускать) тесты
```python
import pytest


@pytest.mark.skip(reason='Have to skip')
def test_1():
    ...
```
#### mark.xfail
Используется, когда ожидается, что тест должен завершиться с ошибкой
```python
import pytest


@pytest.mark.xfail(raises=AssertionError)
def test_1():
    raise AssertionError
```

### Conftest
`Conftest.py` используется для конфигурации запуска тестов и для хранения фикстур. 
Он может находиться как в корневой директории проекта, так и в директориях с тестами.

Фикстуры, находящиеся в корневом `conftest.py` доступны для любых тестов.

Пример `conftest.py`:
```python
import pytest


def pytest_addoption(parser):
    parser.addoption('--run-some-tests', action='store_true', help='')


@pytest.fixture
def run_some_tests(request) -> bool:
    run_some_tests = request.config.getoption('--run-some-tests')
    yield run_some_tests
```
