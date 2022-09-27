# Вопросы для собеса на C# Developer
<details>
    <summary>Абстрактные классы, интерфейсы, рекорды и структуры</summary>

    Абстрактные классы - классы, которые могут содержать как реализацию метода, так и одно его объявление (без реализации). Такие классы позволяют определить контракт, который должен быть переопределен наследниками. Нельзя создавать экземпляры

    Интерфейсы - чисто контракты, объявления методов, которые не содержат реализации (в последних версиях .Net могут содержать реализацию по-умолчанию)

    Структуры - практические те же классы (могут содержать методы, контрукторы), главное отличие - структуры value type (т.е. храниться в стеке), а классы - reference type

</details>

<details>
    <summary>Boxing и Unboxing</summary>

    Превращение value type в reference type и наоборот
</details>

<details>
    <summary>StringBuilder</summary>

    В C# строки неизменяемы. Если мы изменяем строку, то выделяется новая память и создается новая измененная копия, а старая память освобождается. Эта операция дорогая.
    Эффективнее использовать StringBuilder, который собирает данные (строки) и собирает полную строку только в момент вызова его метода ToString()
</details>

<details>
    <summary>Зачем нужен IDisposable?</summary>

    Есть такие ресурсы по типу файла или соединения с базой данных, которые открываются, но которые надо и закрывать. Если этого не делать, то эти ресурсы будут закрыты только тогда, когда сборщик мусора начнет уничтожать объекты. Чтобы гарантировать закрытие ресурсов исользуется IDisposable и конструкция using
</details>

<details>
    <summary>Делегаты</summary>

    Делегаты - это указатели на функцию
</details>

<details>
    <summary>Множественное наследование</summary>

    Можно наследовать один класс и сколько угодно интерфейсов
</details>


<details>
    <summary>SQL Injection. Что такое? Как защититься?</summary>

    SQL injection - это  один из распространённых способов взлома сайтов и программ, работающих с базами данных, основанный на внедрении в запрос произвольного SQL-кода
    Использовать параметры
</details>

<details>
    <summary>Как гарантировать, что объект-синглтон будет создан только один раз?</summary>

    Использовать private конструктор
</details>

<details>
    <summary>Что такое managed и unmanaged код?</summary>

    Managed код - код, написанный на платформе .Net и управляется CLR

    Unmanaged код - код, написанный не на платформе .Net и не управляется CLR
</details>

<details>
    <summary>Что такое Enum?</summary>

    Enum - это тип данных, представляющий собой набор связанных именнованных констант 
</details>

<details>
    <summary>Разница между const и readonly</summary>

    Const - константа, значение котрое нельзя никак изменять и известное на этапе компиляции

    Readonly - значение можно изменять в рантайме только через не статический конструктор
</details>

<details>
    <summary>Разница между ref и out?</summary>

    Ref - передача аргумента по ссылке. Мы можем изменять как хотим исходный элемент (а можем не менять никак)

    Out - передача аргумента по ссылке, но мы обязанны его инициализировать или что то ему присвоить
</details>

<details>
    <summary>Можем ли мы использовать this в статических методах?</summary>

    Нет, не можем, тк this указывает на текущий экземпляр объекта, а статические члены класса не принадлежат ни к какому-либо экземпляру
</details>

<details>
    <summary>Что такое методы расширения? (Extension methods)</summary>

    Методы расширений позволяют добавлять новые методы к классу без создания классов-наследников, рекомпиляции и изменения исходного класса
</details>

<details>
    <summary>Разница между Dispose и Finalize</summary>
    <table>
        <tr>
            <th>Finalize</th>
            <th>Dispose</th>
        </tr>
        <tr>
            <td>Для освобождения unmanaged ресурсов</td>
            <td>Для освобождения unamnaged ресурсов</td>
        </tr>
        <tr>
            <td>Вызывается сборщиком мусора</td>
            <td>Вызывается пользователем</td>
        </tr>
        <tr>
            <td>Принадлежит классу Object</td>
            <td>Принадлежит интерфейсу IDisposable</td>
        </tr>
        <tr>
            <td>Реализуется, когда есть unmanaged ресурсы в классе и нужна гарантия, что они освободяться, когда сборщик мусора уничтожит объект</td>
            <td>Реализуется, когда пишется класс, которым будут пользоваться другие разработчики</td>
        </tr>
    </table>
</details>


<details>
    <summary>Что такое sealed class?</summary>

    Sealed класс нельзя наследовать
</details>