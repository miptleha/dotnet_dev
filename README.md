## Список теоретических вопросов по C# со скрытыми ответами для самопроверки
Ответы могут неточными, но близки к правильным.
Вопросы посвящены [базовому курсу C#](https://metanit.com/sharp/tutorial/), вопросы на анализ кода пропустил (их можно найти по ссылкам, указаным далее).

Нумерация согласно [источнику вопросов](https://metanit.com/sharp/interview/).   
Автор ответов - [@maddevelop](https://teletype.in/@maddevelop). Части: [1](https://teletype.in/@maddevelop/r1t-GTKfV), [2](https://teletype.in/@maddevelop/BkgiE0tzN), [3](https://teletype.in/@maddevelop/H1h78AKG4), [4](https://teletype.in/@maddevelop/HJuu8CFMV), [5](https://teletype.in/@maddevelop/B1v4vCFzE), [6](https://teletype.in/@maddevelop/rytrv-QBN), [7](https://teletype.in/@maddevelop/ByQG3NVBE).   
Дополнил ответами от [Stanislav_Panteleev](http://digital-flame.ru/2018/08/25/c-voprosyi-i-otvetyi-k-sobesedovaniyu-chast-1/) (там над заголовком есть навигация между частями).   
Некоторые пространные ответы сократил и слегка поправил   

Успехов в изучении C# и .NET. Пускай программирование приносит Вам радость!

<details><summary>Вопрос 9. Является ли тип List потокобезопасной (thread-safe) коллекцией?</summary>

>Тип List может быть потокобезопасным в операциях чтения.   
>Пользовательский код должен обеспечивать всю синхронизацию при параллельном добавлении элементов в несколько потоков или удалении элементов из них.
</details>

<details><summary>Вопрос 10. В чем различие между операцией cast (приведения типов) и оператором as?</summary>

>В случае ошибки cast выбрасывает исключение InvalidCastException, а оператор as возвращает null
</details>

<details><summary>Вопрос 11. Какова алгоритмическая сложность для операций чтения и записи для коллекции Dictionary?</summary>

>Чтение очень быстрое, потому что используются хэш-таблицы и сложность в этом случае стремится к O(1).   
>Запись проходит тоже очень быстро (O(1)), в том случае если .Count меньше емкости, если же больше, то скорость стремится к O(n).
</details>

<details><summary>Вопрос 12. В чем различие между ключевыми словами "ref" и "out"?</summary>

>Параметр с ключевым слово out может быть не инициализирован, а параметр с ключевым словом ref обязательно должен быть инииализирован до вызова метода, который использует эти параметры.
</details>

<details><summary>Вопрос 15. В чем отличие необязательных параметров от именованных?</summary>

>Необязательные параметры позволяют опускать аргументы функции, в то время как именованные параметры разрешают передавать аргументы по названию параметра.   
```csharp
public void optionalParamFunc(int p1, int p2 = 2, int p3 = 3); 
optionalParamFunc(1, p3:10); //это эквивалентно optionalParamFunc(1,2,10);
```
</details>

<details><summary>Вопрос 16. Чем отличаются друг от друга классы String и StringBuilder?</summary>

>Объект класса String представляет собой неизменяемую строку.   
>Когда выполняется какой-нибудь метод класса String, система создает новый объект в памяти с выделением ему достаточного места.   
>Объект класса StringBuilder представляет собой динамическую строку.   
>При создании строки StringBuilder выделяет памяти больше, чем необходимо этой строке, а при добавлении к ней каких-либо элементов строка не пересоздается заново.   
>В том случае если выделенной памяти не будет хватать для добавления новых элементов, то емкость объекта будет увеличена.
</details>

<details><summary>Вопрос 17. Какие отличие между значимыми и ссылочными типами?</summary>

>Значимые типы (value type) хранятся в стеке. Стек - это структура данных, которая растет снизу вверх: каждый новый элемент помещаются поверх предыдущего. Время жизни переменных таких типов ограничено их контекстом. Физически стек - это некоторая область памяти в адресном пространстве. А ссылочные типы (reference type) хранятся в куче, это другая область памяти, которую можно представить как неупорядоченный набор различных объектов. Когда создаётся объект ссылочного типа в стеке помещается ссылка на адрес в куче. Когда этот объект перестает использоваться, то ссылка уничтожается. После этого в дело вступает автоматический сборщик мусора: он видит, что на объект в куче нету больше ссылок, и удаляет этот объект и очищает память.
</details>

<details><summary>Вопрос 18. Как и зачем использовать конструкцию using в C#?</summary>

>Ключевое слово using упрощает работу с объектами которые реализуют интерфейс IDisposable.   
>Интерфейс IDisposable содержит один метод .Dispose(), который используется для освобождения ресурсов, которые захватил объект. При использовании using не обязательно явно вызывать .Dispose() для объекта.
</details>

<details><summary>Вопрос 19. В чем отличие использования Finalize и Dispose?</summary>

>Метод Finalize уже определен в базовом для всех типов классе Object, однако данный метод нельзя так просто переопределить. И фактическая его реализация происходит через создание деструктора. Вызывается сборщиком мусора, а точный момент вызова неопределен.   
>Метод Dispose нужен для ручного освобождения ресурсов, через его явный вызов или с помощью using.
</details>

<details><summary>Вопрос 20. В чем основные отличия класса от структуры в языке C#?</summary>

>Основные отличия класса от структуры следующие: 
>    * Структура является размерным типом, а класс – ссылочным.
>    * Все структурные типы неявно наследуются от System.ValueType, они не бывают абстрактными и всегда неявно запечатаны (sealed)
>    * При присваивании переменных структурного типа, создается копия данных
>    * Объявления полей структуры не могут иметь инициализаторов
>    * Различная интерпретация this для структуры и класса
>    * Структура не может содержать конструктор без параметров
>    * Структура не может содержать деструктор
>    * Для ссылочных типов значение по умолчанию – null
>    * При конвертировании между ссылочным и размерным типами происходит упаковка и распаковка.
</details>

<details><summary>Вопрос 21. Как можно сравнить строки в C#?</summary>

```csharp
string s1 = "123";
string s2 = s1.Substring(0, 2) + "3";

//по значению, все варианты сработают
if (s1 == s2) { }
if (s1.CompareTo(s2) == 0) { }
if (s1.Equals(s2)) { }
if (string.Equals(s1, s2)) { }

//по ссылке, не сработают, так сравнивать не надо
if ((object)s1 == (object)s2) { }
if (object.ReferenceEquals(s1, s2)) { }
```
</details>

<details><summary>Вопрос 22. Что такое управляемый код и CLR? Основные требования к управляемому коду.</summary>

>Управляемый код - код программы исполняемый под управлением CLR (Виртуальной машиной .Net).   
>CLR (общеязыковая исполняющая среда) — исполняющая среда для байт-кода CIL (MSIL), в которой компилируются программы, написанные на .NET-совместимых языках программирования (C#, Managed C++, Visual Basic .NET, F# и прочие). CLR является одним из основных компонентов пакета Microsoft .NET Framework.   
>Написанный управляемый код должен быть полностью совместим с CTS(Common Type System), который поддерживают все .Net совместимые языки.
</details>
	
<details><summary>Вопрос 23. Разница IEnumerable<T> и IQueryable<T> при работе с удаленной БД?</summary>

>IEnumerable. Объект IEnumerable представляет набор данных в памяти и может перемещаться по этим данным только вперед.   
>IQueryable. Он располагается в пространстве имен System.Linq. Объект предоставляет удаленный доступ к базе данных и позволяет перемещаться по данным как в прямом порядке от начала до конца, так и в обратном порядке. В процессе же выполнения запроса, происходит оптимизация запроса.
```csharp
IEnumerable<Phone> phoneIEnum = db.Phones;
var phones1 = phoneIEnum.Where(p => p.Id > id).ToList(); //SELECT * FROM PHONES, фильтрация на стороне клиента
IQueryable<Phone> phoneIQuer = db.Phones;
int id = 3;
var phones2 = phoneIQuer.Where(p => p.Id > id).ToList(); //SELECT * FROM PHONES WHERE ID > 3
```
</details>

<details><summary>Вопрос 24. Что такое абстракция и как она связана с ООП?</summary>

>Под абстракцией понимается модель реальной жизни упрощенная для решения конкретной задачи, которая выражена в объекте, т.е. любой объект - это абстракция, т.к. она только частично описывает реальную сущность. Поэтому любой объект можно считать абстракцией и он только частично описывает реальную сущность. Во время преобразования реальных сущностей в объект, он лишается тех характеристик, которые являются несущественными деталями.   
>Например можно составить упрощенный класс человека, который умеет двигаться, а от всего остального мы абстрагируемся (в данным случае несущественно то, что он умеет дышать, кушать, видеть, слышать и т. д.)
</details>

<details><summary>Вопрос 25. Что такое IoC (Inversion of Control/инверсия управления) и для чего она нужна?</summary>

>Inversion of Control (инверсия управления) — это некий абстрактный принцип, набор рекомендаций для написания слабо связанного кода. Суть которого в том, что каждый компонент системы должен быть как можно более изолированным от других, не полагаясь в своей работе на детали конкретной реализации других компонентов.
</details>
	
<details><summary>Вопрос 26. Что такое DI (Dependency Injection) контейнер?</summary>

>DI контейнер это один из способов реализации принципа IoC. Этот контейнер знает о всех интерфейсах и их реализациях в системе и умеет их сопоставлять. Перед началом работы с ним необходимо зарегистрировать известные типы и их сопоставления(интерфейс-->реализация).
</details>

<details><summary>Вопрос 27. Какие реализации DI контейнеров вы знаете на C#. Какой DI контейнер является лучшим?</summary>

>Castle Windsor, Autofac, Ninject, Unity...и так далее, на самом деле их очень много. На счет того, какой из них лучший не совсем корректный вопрос. Все зависит от конкретной реализации.
</details>

<details><summary>Вопрос 28. Что подразумевается под свойствами в C#?</summary>

>В C# существуют специальные методы доступа, которые и именуются свойствами. Они обеспечивают простой доступ к полям класса для получения или установки их значения.
>Определение свойства содержит блоки get и set. В блоке get возвращается значение поля, а в блоке set устанавливается с помощью параметра value, которое представляет передаваемое значение.
</details>

<details><summary>Вопрос 29. Что такое assembly manifest (манифест сборки)?</summary>

>Манифест сборки содержит следующую информацию (первые чертыре составляют удостоверение сборки):
>    * Имя сборки
>    * Номер версии: основной и дополнительный номера. Используется для управления версиями
>    * Язык и региональные параметры: информация о языке и региональных параметрах, которые поддерживает сборка
>    * Информация о строгом имени: открытый ключ издателя
>    * Список всех файлов сборки: хэш и имя каждого из входящих в сборку файлов
>    * Список ссылок на другие сборки, которые использует текущая сборка
>    * Список ссылок на типы, используемые сборкой

</details>
	
<details><summary>Вопрос 30. Что такое GAC? Возможно ли поместить два файла с одинаковым именем в Global Assembly Cache?</summary>

>GAC (Global Assembly Cache) - глобальный кэш сборок, место где хранятся разделяемые сборки.
>В GAC нельзя помещать полностью одинаковые сборки (сборки с полностью совпадающим сложным именем). Сложное имя сборки состоит из нескольких частей:
>    * Имя сборки без расширения
>    * Номер версии. Благодаря разграничению по версии можно хранить разные версии одной и ой же сборки
>    * Открытый ключ
>    * Необязательное значение для культуры (при локализации сборки)
>    * Цифровая подпись, которая создается с помощью хэш-значения содержимого сборки и значения секретного ключа. Секретный ключ представляет собой файл с расширением *.snk.
>Если совпадают у двух сборок только имена сборки, а все остальное отличается, то их можно помещать в GAC вместе.
</details>
	
<details><summary>Вопрос 31. Какие модификаторы доступа существуют в C#?</summary>

> В C# применяются следующие модификаторы доступа:   
>    * public: публичный, общедоступный класс или член класса. Такой член класса доступен из любого места в коде, а также из других программ и сборок.
>    * private: закрытый класс или член класса. Представляет полную противоположность модификатору public. Такой закрытый класс или член класса доступен только из кода в том же классе или контексте.
>    * protected: такой член класса доступен из любого места в текущем классе или в производных классах. При этом производные классы могут располагаться в других сборках.
>    * internal: класс и члены класса с подобным модификатором доступны из любого места кода в той же сборке, однако он недоступен для других программ и сборок (как в случае с модификатором public).
>    * protected internal: совмещает функционал двух модификаторов. Классы и члены класса с таким модификатором доступны из текущей сборки и из производных классов.
>    * private protected: такой член класса доступен из любого места в текущем классе или в производных классах, которые определены в той же сборке.
</details>
	
<details><summary>Вопрос 32. Что такое Boxing и Unboxing?</summary>

>Упаковка представляет собой процесс неявный преобразования типа значения (хранящегося в стеке) в тип object. Когда тип значения упаковывается средой CLR, она создает оболочку значения внутри System.Object и сохраняет ее в управляемой куче. Обратная операция распаковки осуществляется явным преобразованием object в тип значения. Если упакованный объект не соответствует требуемому типу, то выбрасывается исключение InvalidCastException.
</details>
	
<details><summary>Вопрос 33. В чем суть полиморфизма?</summary>

>Полиморфизм – способность функции обрабатывать данные разных типов.   
>    * Ad-hoc полифорфизм (перегрузка функций, приведение типа) — можно создать несколько методов с одним именем и разными аргументами, примитивные типы могут неявно приводиться.
>    * Параметрический полиморфизм (обобщённое программирование) — можно создать полиморфные (обобщённые) типы.
>    * Полиморфизм включения (наследование) — интерфейсы, наследование классов, виртуальные функции.
</details>
	
<details><summary>Вопрос 34. Какие типы можно использовать в предложении foreach?</summary>

>Можно использовать типы, которые реализуют интерфейс IEnumerable или IEnumerable\<T\>.   
>Либо же к любым типам которые удовлетворяют следующим условиям:
>    * Включают открытый метод GetEnumerator без параметров с классом, структурой или тип интерфейсом в качестве возвращаемого значения;
>    * Тип возвращаемого значения метода GetEnumerator должен содержать открытое свойство Current и открытый метод MoveNext без параметров с типом возвращаемого значения Boolean.
</details>
	
<details><summary>Вопрос 35. Чем отличается event от delegate?</summary>

>Отличаются так же, как отличаются свойства от полей.   
>Событие может быть только членом класса и может быть запущено только в классе, в котором объявлено.
>Кроме того, подписчик события не может отписать других подписчиков.   
>Событие реализуется компилятором в виде приватного поля-делегата и двух публичных методов подписки/отписки на событие.

</details>
	
<details><summary>Вопрос 36. Может ли класс реализовать два интерфейса, у которых объявлены одинаковые методы? Если да, то каким образом?</summary>

> Может. Общие методы при этом надо реализовывать один раз неявно или два раза явно (с указанием имени интерфейса). При явной реализации метод нельзя будет вызывать без приведения экземпляра класса к интерфейсу (если только не будет третьей реализации метода в классе).   
>Если два метода интерфейса выполняют разные действия, то неявная реализация интерфейсов может быть некорректной.
</details>
	
<details><summary>Вопрос 37. Объясните разницу между System.Array.CopyTo() и System.Array.Clone()?</summary>

>   * CopyTo требует наличия выходного массива, тогда как Clone создает новый массив. 
>   * CopyTo позволяет указывать индекс элемента, начиная с которого производить копирование. 
</details>
	
<details><summary>Вопрос 38. Что такое абстрактный класс? В каком случае вы обязаны объявить класс абстрактным?</summary>

>Абстрактный класс - это класс, имеющий неполную реализацию, которую реализует его неабстрактный наследник. Нельзя создать экземпляр абстрактного класса.   
>Абстрактные классы нужны для того, чтобы выделять общий функционал от нескольких классов в обособленный класс. От этого отдельного класса потом можно унаследовать либо просто сигнатуру функционала, либо вместе с реализацией.   
>Класс обязательно нужно объявлять как абстрактный когда он содержит абстрактные члены.
</details>
	
<details><summary>Вопрос 39. Назовите отличия между интерфейсом и абстрактным классом?</summary>

>Интерфейс — это абстрактный класс, у которого ни один метод не реализован, все они публичные и нет переменных класса.   
>Абстрактные классы и интерфейсы используются в наследовании, при этом разрешено наследование нескольких интерфейсов, но только одного класса.
</details>
	
<details><summary>Вопрос 40. В чем разница между абстрактными и виртуальными классами? Между виртуальными и абстрактными методами?</summary>

>Абстрактные классы это класс помеченный ключевым словом abstract. В абстрактном классе содержатся абстрактные члены (методы, свойства, индексаторы, события) они не имеют внутренней реализации и выступают в роли интерфейса. Они так же обязаны быть помечены ключевыми словом abstract. При наследовании от абстрактного класса, класс наследник получает все свойства своего класса родителя, а если в родительском классе есть еще и абстрактные члены, то в классе наследнике обязательно их нужно переопределять.   
>Виртуальный класс, это просто класс в котором есть виртуальные члены (методы, свойства...) Виртуальные члены помечаются модификатором virtual и имеют внутреннюю реализацию, которая может быть переопределена в классе наследнике.
</details>
	
<details><summary>Вопрос 41. Что означает модификатор virtual?</summary>

>Модификатор virtual служит для того, чтобы помечать виртуальные методы или свойства в классе родителя. Виртуальные методы (свойства) - это такие методы, которые мы хотим переопределить в классах наследниках. А чтобы переопределить метод в классе-наследнике, этот метод определяется с модификатором override. Переопределенный метод в классе-наследнике должен иметь тот же набор параметров, что и виртуальный метод в базовом классе.   
>Переопределять можно и невиртуальные методы, но тогда выбор метода (родителя или наследника) будет осуществляться статически во время компиляции на основании типа переменной, а не типа объекта, хранящейся в ней.
</details>
	
<details><summary>Вопрос 42. В чем разница инкапсуляции и сокрытия?</summary>

>Инкапсуляция - одна из парадигм ООП. Она представляет собой способность языка упаковывать определённые участки кода в контейнеры, исключая возможность внешнего мира нарушения целостности данного кода. Основной единицей инкапсуляции в C# является класс. Инкапсуляция позволяет структурировать код и помогает обезопасить его от многих возможных проблем, относительно защиты данных и информации.   
>Сокрытие же скрывает детали о процессе. Для определения прав доступа к данным в классе и к классу непосредственно используются модификаторы доступа. Получается, что использование этих модификаторов и есть то самое сокрытие.
>Но сам термин "сокрытие" лучше употреблять в контексте методов. Сокрытие метода представляет собой реализация тела метода в дочернем классе, сигнатура которого соответствует сигнатуре метода в родительском классе. Для сокрытия применяется ключевое слово "new".
</details>
	
<details><summary>Вопрос 43. Что такое частные и общие сборки?</summary>

>Частные сборки:
>    * Видны только самому приложению
>    * Нет необходимости заботиться об уникальном имени во всем глобальном пространстве имен
>    * Не нужно делать записей в реестре при развертывании приложения
>    * Сборки просто копируются в директорию приложения или в подчинённую директорию
>    * Общая среда выполнения (CLR) при запуске приложения прочитает его манифест и определит какие сборки необходимы. Затем будет произведен поиск нужной сборки по директории приложения (процесс зондирования)
>Общие сборки:
>    * Общие сборки могут быть использованы сразу несколькими приложениями
>    * Сборка должна иметь строгое имя (strong name)
>    * Сборка должна быть помещена в общедоступное место – Global Assembly Cache (GAC, глобальный кэш сборок)
</details>
	
<details><summary>Вопрос 44. Что такое .Net Framework?</summary>

>.NET Framework — программная платформа, выпущенная компанией Microsoft в 2002 году. Основой платформы является общеязыковая среда исполнения Common Language Runtime (CLR), которая подходит для разных языков программирования. Функциональные возможности CLR доступны в любых языках программирования, использующих эту среду.

</details>
	
<details><summary>Вопрос 45. Чем управляемый код (managed code) отличается от неуправляемого (unmanaged code)?</summary>

>Управля́емый код (managed code) — термин, введённый фирмой Microsoft, для обозначения кода программы, исполняемой под «управлением» виртуальной машины .NET — Common Language Runtime или Mono. При этом машинный код называется неуправля́емым кодом (unmanaged code).   
>Слово «управляемый» относится к методу обмена информацией между программой и исполняющей средой. Оно означает, что в любой точке исполнения управляющая среда может приостановить исполнение и получить информацию, специфичную для текущего состояния. Необходимая для этого информация представлена в управляемом коде на языке Intermediate Language и в связанных с этим кодом метаданных.   
</details>
	
<details><summary>Вопрос 46. LINQ lazy loading, eager loading в чем разница?</summary>

>В случае lazy loading (ленивая загрузка), зависимые таблицы (дочерние объекты) не загружаются автоматически с родительскими, а загрузятся в тот момент, когда они понадобятся. В LINQ по умолчанию используется lazy loading.
>В случае eager loading (жадной загрузки), зависимые объекты загружаются автоматически с родительской таблицей. Для того, чтобы использовать eager loading нужно применить метод Include().
</details>
	
<details><summary>Вопрос 47. Можно ли запретить наследование от своего собственного класса?</summary>

>Для того, чтобы запретить наследоваться от класса необходимо объявить его с модификатором sealed.
</details>

<details><summary>Вопрос 48. Можно ли разрешить наследование класса, но запретить переопределение метода?</summary>

>Можно для второго класса в иерархии наследования, если переопределяем виртуальный метод как sealed override, тогда дальнейшее переопределение по цепочке наследования запрещено.
</details>
	
<details><summary>Вопрос 49. Определение паттерна синглтон</summary>

>Одиночка (Singleton, Синглтон) - порождающий паттерн, который гарантирует, что для определенного класса будет создан только один объект, а также предоставит к этому объекту точку доступа. Используется тогда, когда необходимо, чтобы для класса существовал только один экземпляр. Синглтоны бывают потокобезопасные и нет, с простой и отложенной инициализацией.
```csharp
class Singleton
{
    private static readonly Singleton _instance = new Singleton();
    private Singleton() {}
    static Singleton() {}
    public static Singleton Instance { get { return _instance; } }
}
```
</details>
	
<details><summary>Вопрос 50. Thread, task, примеры использования?</summary>

>Класс Thread создает и контролирует поток. На входе указывается метод, который будет выполняться в потоке.   
>Класс Task позволяет запускать отдельную продолжительную задачу. Она запускается асинхронно в одном из потоков из пула потоков, но ее можно запускать и синхронно.
```csharp
var t = new Thread(() => Thread.Sleep(1000));
t.IsBackground = false; //основной поток, система сама ожидает его завершение
t.Start();
Task.Run(() => Task.Delay(1000)).Wait(); //с использованием TPL
```
</details>
	
<details><summary>Вопрос 51. Что такое интеграционные тесты и unit-тесты?</summary>

>Модульное тестирование: проверка отдельного модуля (класса, библиотеки) приложения независимо от другого модуля. Позволяет провести регресионное тестирование (при внесении изменений в модуль, убедиться, что он по прежнему работает).   
>Интеграционное тестирование: программные модули объединяются и тестируются в группе. Эти тесты проверяют правильность взаимодействия нескольких подсистем (например, двух классов). Проводится после модульного тестирования.   
>Системное тестирование: проверяется все приложение в целом на соответсвие требованиям по принципу черного ящика (без учета внутреннего строения приложения).
</details>
	
<details><summary>Вопрос 52. Что такое MVVM?</summary>

>Шаблон MVVM (Model-View-ViewModel) позволяет отделить логику приложения от визуальной части, используется в WPF. Основные компоненты:
>    * Модель (Model) описывает используемые в приложении данные. Модели могут содержать логику, непосредственно связанную этими данными, например, логику валидации свойств модели.   
>    * Представление (View) — определяет визуальный интерфейс (кнопки, текстовые поля и прочие визуальные элементы), через который пользователь взаимодействует с приложением.
>    * Модель Представления (ViewModel) — связывает модель и представление через механизм привязки данных. Если в модели изменяются значения свойств, автоматически идет изменение отображаемых данных в представлении, хотя напрямую модель и представление не связаны. ViewModel также содержит логику по получению данных из модели, которые потом передаются в представление. И также VewModel определяет логику по обновлению данных в модели.
</details>
	
<details><summary>Вопрос 54. Когда использовать StringBuilder предпочтительнее, чем string?</summary>

>StringBuilder предпочтительнее использовать если строка часто изменяется.
</details>
	
<details><summary>Вопрос 59. Какой уровень доступа имеют поля класса, если модификатор доступа не указан?</summary>

>Если не указывать модификатор доступа для поля класса, то по умолчанию они объявляются с модификатором private. Для всех модификаторов доступа действует правило: если не указан модификатор, то устанавливается максимально строгий, при котором код будет компилироваться. 
</details>
	
<details><summary>Вопрос 60. Каким образом можно присвоить значения полям, которые помечены ключевым словом readonly?</summary>

>Из конструктора, либо в месте объявления поля, приравнивая ему какое-то значение.
</details>
	
<details><summary>Вопрос 61. Какая из операций linq исключает дублирование одинаковых элементов в выходной последовательности?</summary>

>Операция Distinct удаляет дублированные элементы из входной последовательности.
</details>
	
<details><summary>Вопрос 62. С помощью какого ключевого слова осуществляется блокировка одновременного выполнения определенных участков кода несколькими потоками?</summary>

>Для осуществления блокировки одновременного выполнения определенных участков кода несколькими потоками используется ключевое слово lock. lock определяет блок, внутри которого весь код становится недоступным для других потоков до завершения работы текущего потока.
</details>
	
<details><summary>Вопрос 63. Какой интерфейс должен реализовать класс, чтобы к переменной данного типа был применим оператор foreach?</summary>

>Оператор foreach может применяться для переменных, которые реализуют интерфейс IEnumerable или IEnumerable<T>, либо к экземпляру любого типа, удовлетворяющим условиям:
>    * должен включать открытый метод GetEnumerator без параметров с классом, структурой или типом интерфейса в качестве возвращаемого значения;
>    * тип возвращаемого значения метода GetEnumerator должен содержать открытое свойство Current и открытый метод MoveNext без параметров с типом возвращаемого значения Boolean.
</details>
	
<details><summary>Вопрос 64. Когда вызывается статический конструктор класса?</summary>

>Статический конструктор вызывается автоматически для инициализации класса перед созданием первого экземпляра типа или при первом обращении к каким-либо статическим членам.
</details>
	
<details><summary>Вопрос 65. Чем отличаются константы и поля, доступные только для чтения?</summary>

>Константы инициализируются только во время компиляции, а поля, доступные для чтения, могут инициализироваться и в месте определения и во время выполнения в конструкторе.
</details>

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fmiptleha%2Fdotnet_dev&count_bg=%230C7DBD&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com)

