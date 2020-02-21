# RedisMap
Основная идея всей задачи укладывается в одно предложение:
сделать `RedisMap` - корректную реализацию `Map<String,String>` с хранением данных в **Redis**. Задача имеет ряд усложнений.

1. Реализовать `RedisMap` таким образом, чтобы любой код, принимающий `Map<String,String>`,
продолжил бы работать (функционально) так же при передаче в него `RedisMap`.  
Подсказка: `HashMap<String,String>` - самая близкая по смыслу к `RedisMap` реализация в Java.  
Примечание: должно быть возможным создавать `RedisMap` в любых количествах (как это можно делать с `HashMap`), а данные в каждой структуре будут свои.
2. Удалением объектов в Java занимается сборщик мусора.
Необходимо придумать способ автоматической очистки Redis при удалении объекта `RedisMap` в Java.
3. Придумать и реализовать способ использования одного набора «key:value» из нескольких приложений через `RedisMap`.
Например, в одном приложении `RedisMap` наполняется объектами, а в другом - они используются.  
Примечание: при реализации важно не сломать сценарии из предыдущих двух пунктов.

Для взаимодействия с Redis из Java можно использовать любой из клиентов, например, [Jedis](https://github.com/xetorthio/jedis).

Для удобства в проекте подготовлена заготовка класса `RedisMap` и базовый тест для неё.

Примечания
* Возможно, что в ходе реализации потребуется переопределить какие-либо другие методы из `Map`.
* Для проверки корректности реализации `RedisMap` базового теста недостаточно, поэтому необходимо позаботиться о написании своих тестов.