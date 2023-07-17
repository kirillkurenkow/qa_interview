# Вопросы для QA собеседования

## Категории
* [Python](/Python)
  * [Базовые вопросы](/Python/Базовые%20вопросы.md)
    * [Основные типы данных](/Python/Базовые%20вопросы.md/#основные-типы-данных)
    * [Операторы](/Python/Базовые%20вопросы.md/#операторы)
      * [Математические операторы](/Python/Базовые%20вопросы.md/#математические-операторы)
      * [Логические операторы](/Python/Базовые%20вопросы.md/#логические-операторы)
    * [List, dict, set comprehension](/Python/Базовые%20вопросы.md/list-dict-set-comprehension)
    * [Итераторы и генераторы](/Python/Базовые%20вопросы.md/#итераторы-и-генераторы)
      * [Итераторы](/Python/Базовые%20вопросы.md/#итераторы)
      * [Итерируемые объекты](/Python/Базовые%20вопросы.md/#итерируемые-объекты)
      * [Коллекции](/Python/Базовые%20вопросы.md/#коллекции)
      * [Генераторы](/Python/Базовые%20вопросы.md/#генераторы)
      * [Разница между итератором и генератором](/Python/Базовые%20вопросы.md/#разница-между-итератором-и-генератором)
    * [Функции](/Python/Базовые%20вопросы.md/#функции)
      * [Что такое функции высшего порядка](/Python/Базовые%20вопросы.md/#что-такое-функции-высшего-порядка)
      * [`args` и `kwargs`](/Python/Базовые%20вопросы.md/#args-и-kwargs)
      * [`lambda` функции](/Python/Базовые%20вопросы.md/#lambda-функции)
      * [Замыкания](/Python/Базовые%20вопросы.md/#замыкания)
      * [Декораторы](/Python/Базовые%20вопросы.md/#декораторы)
        * [Декораторы с аргументами](/Python/Базовые%20вопросы.md/#декораторы-с-аргументами)
        * [`functools.wraps`](/Python/Базовые%20вопросы.md/#functoolswraps)
    * [Исключения](/Python/Базовые%20вопросы.md/#исключения)
      * [Дерево исключений](/Python/Базовые%20вопросы.md/#дерево-исключений)
    * [Варианты форматирования строк](/Python/Базовые%20вопросы.md/#варианты-форматирования-строк)
      * [Форматирование с помощью оператора `%`](/Python/Базовые%20вопросы.md/#форматирование-с-помощью-оператора-)
      * [Форматирование с помощью метода `str.format()`](/Python/Базовые%20вопросы.md/#форматирование-с-помощью-метода-strformat)
      * [Форматирование с помощью f-строк](/Python/Базовые%20вопросы.md/#форматирование-с-помощью-f-строк)
    * Параллельный код
      * asyncio
      * threading
      * multiprocessing
  * [ООП](/Python/ООП.md)
    * [Magic или dunder методы](/Python/ООП.md/#magic-или-dunder-методы)
      * [Методы для инициализации и конструктора](/Python/ООП.md/#методы-для-инициализации-и-конструктора)
        * [Разница между `__new__` и `__init__`](/Python/ООП.md/#разница-между-__new__-и-__init__)
      * [Унарные операторы и функции](/Python/ООП.md/#унарные-операторы-и-функции)
      * [Расширенное присвоение](/Python/ООП.md/#расширенное-присвоение)
      * [Методы преобразования типов](/Python/ООП.md/#методы-преобразования-типов)
      * [Строковые методы](/Python/ООП.md/#строковые-методы)
      * [Методы атрибутов](/Python/ООП.md/#методы-атрибутов)
      * [Методы математических операторов](/Python/ООП.md/#методы-математических-операторов)
    * [MRO и наследование](/Python/ООП.md/#mro-и-наследование)
      * [Функция `super`](/Python/ООП.md/#функция-super)
    * [Миксины (Mixin)](/Python/ООП.md/миксины-mixin)
    * [property](/Python/ООП.md/#property)
    * [Метаклассы](/Python/ООП.md/#метаклассы)
      * [Как работают](/Python/ООП.md/#как-работают)
      * [Зачем использовать](/Python/ООП.md/#зачем-использовать)
  * [Модули](/Python/Модули.md)
    * [Что такое модуль](/Python/Модули.md/#что-такое-модуль)
    * [Что такое пакет](/Python/Модули.md/#что-такое-пакет)
    * [Как происходит поиск модулей при импорте](/Python/Модули.md/#как-происходит-поиск-модулей-при-импорте)
    * PyTest
      * conftest
      * fixture
    * Selenium
    * collections
      * namedtuple
      * defaultdict
      * OrderedDict
      * Counter
      * ChainMap
      * deque
    * itertools
      * count
      * cycle
      * repeat
      * starmap
      * accumulate
      * dropwhile
      * takewhile
      * filterfalse
      * compress
      * islice
      * chain
      * zip_longest
      * tee
      * pairwise
      * groupby
      * permutations
      * combinations
      * combinations_with_replacement
      * product
    * functools
      * cache
      * lru_cache
      * partial
      * wraps
    * re
    * requests
    * csv
    * json
  * [GIL](/Python/GIL.md)
* [QA](/QA.md)
  * [Основные понятия](/QA.md/#основные-понятия)
    * [Баг](/QA.md/#баг)
      * [Жизненный цикл бага](/QA.md/#жизненный-цикл-бага)
      * [Серьезность (Severity) и приоритет (Priority)](/QA.md/#серьезность-severity-и-приоритет-priority)
      * [Градация серьезности дефекта](/QA.md/#градация-серьезности-дефекта)
  * [Пирамида тестирования](/QA.md/#пирамида-тестирования)
  * [Техники тест дизайна](/QA.md/#техники-тест-дизайна)
    * [Эквивалентное разделение](/QA.md/#эквивалентное-разделение)
    * [Анализ граничных значений](/QA.md/#анализ-граничных-значений)
    * [Доменный анализ](/QA.md/#доменный-анализ)
    * [Предугадывание ошибки](/QA.md/#предугадывание-ошибки)
    * [Причина-следствие](/QA.md/#причина-следствие)
    * [Сценарий использования](/QA.md/#сценарий-использования)
    * [Исчерпывающее тестирование](/QA.md/#исчерпывающее-тестирование)
    * [Попарное тестирование](/QA.md/#попарное-тестирование)
    * [Тестирование на основе состояний и переходов](/QA.md/#тестирование-на-основе-состояний-и-переходов)
    * [Таблица принятия решений](/QA.md/#таблица-принятия-решений)
* [GIT](/GIT.md)
  * [Основные команды](/GIT.md/#основные-команды)
    * [git add](/GIT.md/#git-add)
    * [git status](/GIT.md/#git-status)
    * [git diff](/GIT.md/#git-diff)
    * [git commit](/GIT.md/#git-commit)
    * [git reset](/GIT.md/#git-reset)
    * [git clean](/GIT.md/#git-clean)
    * [git branch](/GIT.md/#git-branch)
    * [git checkout](/GIT.md/#git-checkout)
    * [git merge](/GIT.md/#git-merge)
    * [git stash](/GIT.md/#git-stash)
    * [git fetch](/GIT.md/#git-fetch)
    * [git pull](/GIT.md/#git-pull)
    * [git push](/GIT.md/#git-push)
    * [git cherry-pick](/GIT.md/#git-cherry-pick)
    * [git rebase](/GIT.md/#git-rebase)
    * [git revert](/GIT.md/#git-revert)
    * [git grep](/GIT.md/#git-grep)
* [Linux](/Linux.md)
  * [Основные команды](/Linux.md/#основные-команды)
    * [cd](/Linux.md/#cd)
    * [clear](/Linux.md/#clear)
    * [history](/Linux.md/#history)
    * [man](/Linux.md/#man)
    * [sudo](/Linux.md/#sudo)
    * [sudo su](/Linux.md/#sudo-su)
    * sudo !!
    * [kill](/Linux.md/#kill)
    * [killall](/Linux.md/#killall)
    * [top](/Linux.md/#top)
    * [cat](/Linux.md/#cat)
    * [chmod](/Linux.md/#chmod)
    * [chown](/Linux.md/#chown)
    * [file](/Linux.md/#file)
    * [nano](/Linux.md/#nano)
    * [rename](/Linux.md/#rename)
    * [touch](/Linux.md/#touch)
    * [mkdir](/Linux.md/#mkdir)
    * [rmdir](/Linux.md/#rmdir)
    * [rm](/Linux.md/#rm)
    * [cp](/Linux.md/#cp)
    * [mv](/Linux.md/#mv)
    * [grep](/Linux.md/#grep)
* [SQL](/SQL.md)
  * [Примеры запросов](/SQL.md/#примеры-запросов)
    * [SELECT](/SQL.md/#select)
    * [UPDATE](/SQL.md/#update)
    * [DELETE](/SQL.md/#delete)
    * [INSERT](/SQL.md/#insert)
    * [CREATE TABLE](/SQL.md/#create-table)
    * [DROP TABLE](/SQL.md/#drop-table)
  * [JOINы](/SQL.md/#joinы)
    * [Inner join](/SQL.md/#inner-join)
    * [Left и right join](/SQL.md/#left-и-right-join)
    * [Full join](/SQL.md/#full-join)
* [Network](/Network.md)
  * [Модель OSI](/Network.md/#модель-osi)
  * [Протоколы](/Network.md/#протоколы)
    * [HTTP](/Network.md/#http)
      * [Методы HTTP запросов](/Network.md/#методы-http-запросов)
      * [Коды ответа HTTP](/Network.md/#коды-ответа-http)
        * [Описание некоторых кодов ответа HTTP](/Network.md/#описание-некоторых-кодов-ответа-http)
    * [TCP и TCP/IP](/Network.md/#tcp-и-tcpip)
    * [DHCP](/Network.md/#dhcp)
    * [DNS](/Network.md/#dns)
  * [API](/Network.md/#api)
    * [REST](/Network.md/#rest)
      * [Основные принципы REST](/Network.md/#основные-принципы-rest)
    * [RPC](/Network.md/#rpc)
      * [XML-RPC и SOAP](/Network.md/#xml-rpc-и-soap)
      * [JSON-RPC](/Network.md/#json-rpc)
      * [gRPC](/Network.md/#grpc)
  * [Сокеты](/Network.md/#сокеты)
* [Другие ворпосы](/Other.md)
  * [CI/CD](/Other.md/#cicd)
  * [Принципы программирования](/Other.md/#принципы-программирования)
    * [DRY](/Other.md/#dry)
    * [KISS](/Other.md/kiss)
    * [SOLID](/Other.md/#solid)
  * Криптография и шифрование
  * Хэширование
  * Разные вопросы
    * Разница между стеком и очередью
    * Какая разница между аутентификацией и авторизацией
