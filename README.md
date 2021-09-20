# .NET разработка

Данный текст является дневником месячного марафона подготовки к собеседованиям по вакансии [программист C#](https://hh.ru/search/vacancy?area=1&fromSearchLine=true&st=searchVacancy&text=%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%81%D1%82+c%23).  
<b>Старт марафона</b>: 20.09.2021, <b>Окончание</b>: до ноября не забрасывать.  
Откладываю все несрочные дела и интересы. Язык C# выбран как наиболее знакомый и приятный, если марафон окажется успешным, повторю его для других языков.

## О себе

Я работаю программистом .NET уже много лет с момента появления этой технологии (в свое время получил пинок под зад как разработчик C++ и пришлось найти язык попроще). На текущей работе уже около 10 лет в отделе веб-разработки (занимаюсь сервисами). Здесь меня любят, уважают, хорошо платят. Но всякое в жизни может быть, расслабляться нельзя.

Недавно общался со знакомым директором, он посоветовал: "найти работу не проблема, только нужно готовиться к собеседованию". Человек умный, к его мнению я прислушиваюсь. Тупо, как в молодости, без подготовки устраиваться на первую работу, куда возьмут, не хочу. Да и переходить в другую компанию тоже не хочу (тут свободный удаленный график).

Осознаю, что не знаю многих вещей (недавно на работе предложили проект на React под .NET Core для реализации в сжатые сроки, я отказался, понимая, что знаний недостаточно). Пробелов очень много, но учиться не получается. Поэтому вижу выход в данном марафоне.

## План марафона

Будем танцевать от вакансий, что в них требуется. Также посмотрим советы для кандидатов, примеры вопросов на собеседовании (как умные люди, опускаться до заучивания ответов не будем). 

Необходимо в общих чертах освоить стек технологий для C# программиста. Все меняется, вчера я был разработчиком толстых клиентов, сегодня веб-разработчик. Что будет завтра я не знаю. Появляются новые технологии (например, вместо верстки в тренде использование веб-фреймвоков).

Но прежде чем начинать, рассмотрим основы языка C#. Мне, допустим, это не нужно. Но надо сразу закрыть вопрос, чтобы безобидный вопрос на собеседовании и вытянувшиеся лица не закрыли перед нами двери.

## Основы языка C#

Времени читать книги у нас нет. Нужно какое-нибудь онлайн руководство со сжатой подачей информации о самом языке. Первое на что можно обратить внимание, это курс [Метанита](https://metanit.com/sharp/tutorial/). Опять же не заморачиваемся, быстро просматриваем, выборочно повторяя примеры. Не отвлекаемся и не закапываемся, помним о сжатых сроках, поэтому не тормозим и не медитируем над текстом.







https://docker-curriculum.com/

* Общие требования и советы
* Обзор вакансий
* Список вопросов
* 

Изучение .NET я бы разбил на следующие разделы, которые по моему мнению следует изучать строго друг за другом.

* [Общие принципы для разработчика](Principles.md)
* [Обзор C#](Review.md)
* Базовые классы
* Фреймворки
* Смежные технологии

Даже человек с большим опытом программирования на C# скорей всего знает лишь часть .NET, что же говорить про новичка, которому будет совсем непросто.

Кроме того, часто подразумевается, что C# программист - это fullstack специалист, он и серверный код пишет, и клиентский, и БД настраивает, и интегрируется с другими программами (не обязательно написанных на .NET). Нужно много чего знать помимо .NET.

Овладев некоторым объемом знаний по .NET, можно начинать готовиться к собеседованиям. Этой теме будет посвящен отдельный раздел.

Я не могу подробно рассматривать каждую тему (да и не знаю всех тонкостей), получится много скучного текста. Данное пособие - это вспомогательный учебный материал, который облегчит ваше самостоятельное изучение .NET.

Встает вопрос, а как лучше построить это обучение? Читать книги, смотреть видео-уроки, поступить на платные курсы? Может устроиться стажером? Лично я считаю, что можно обучаться как угодно, все зависит не от учителя, а от ученика. Прог

# Что нужно знать .net разработчику

.NET разработчик - это fullstack или backend разработчик на языке [C#](https://ru.wikipedia.org/wiki/C_Sharp) - быстром и простом языке.
Используется не для сайтов-визиток, а для полноценных корпоративных приложений. Приложения могут быть как целиком толстым клиентом (WinForms, WPF), либо серверная часть + тонкий клиент (ASP.NET + JS).
Для хранения данных используются СУБД (MS SQL, MySql, Postgre, Oracle), необходимо уметь ими пользоваться тоже.

# Сам язык

Технологий .NET так много, что все их изучить очень сложно. Но все они внутри себя используют язык программирования Си-шарп (C#).
Это статический, компилируемый язык.
Начнем со [спецификации](https://docs.microsoft.com/ru-ru/dotnet/csharp/language-reference/language-specification/introduction) языка.
Этих знаний достаточно, чтобы уметь читать исходный код на этом языке, а также писать свои классы и реализовывать алгоритмы.
Обладая общими знаниями по C#, можно пробовать проходить [собеседования](https://bool.dev/blog/detail/voprosy-na-sobesedovanii-po-c) по этому языку. Еще пример [вопросов](https://habr.com/ru/post/328504/), или [такие](https://zen.yandex.ru/media/id/5c55c96186e4a700adce7631/voprosy-na-sobesedovaniiah-po-c-i-net-na-poziciiu-juniormiddle-chast-1-5c5881a7394f1500aae3995b).
Можно попрактиковаться на таких [задачах](https://metanit.com/sharp/practice/1.1.php). Вот такие [задачи](http://cppstudio.com/cat/285/) (они для C++, но их можно решать и на любом другом языке).
Если искать задачу не хочется, можно зарегистрироваться на [codewars](https://www.codewars.com/) и порешать задачки там.

# Настройка окружения

Понадобится среда разработки ([IDE](https://ru.wikipedia.org/wiki/%D0%98%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%B0%D1%8F_%D1%81%D1%80%D0%B5%D0%B4%D0%B0_%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8)), которая включает в себя компилятор, редактор кода, отладчик и все необходимое для запуска программ.
Рекомендуется пользоваться [Visual Studio](https://visualstudio.microsoft.com/ru/thank-you-downloading-visual-studio/?sku=Community). При установке выбрать необходимые фреймвоки (можно будет добавить потом).
Если слабый интернет или нет места на диске, то используйте редактор [Visual Code](https://code.visualstudio.com/docs/?dv=win), проведя его [настройку](https://code.visualstudio.com/docs/languages/csharp). Это упрощенный универсальный редактор для любых языков программирования. 
[Начните](https://docs.microsoft.com/ru-ru/dotnet/core/tutorials/with-visual-studio) с консольных приложений, они не требуют никаких дополнительных знаний, кроме [базовой библиотеки .NET](https://docs.microsoft.com/ru-ru/previous-versions/gg145045(v=vs.110))

# О языке

* https://www.youtube.com/watch?v=gaFYO6ccRpA


# В инете на эту тему

* https://zen.yandex.ru/media/id/5caf292624db4c00b49fb778/vakansiia-aspnetrazrabotchik-5cb6e0e4eb4c5d00b3cb401d
* https://itmozg.ru/news/1301/
* https://klever.blog/from-qa-to-net/
* https://habr.com/ru/post/451084/

# Вопросы на собеседовании

* https://techrocks.ru/2021/01/12/net-job-interview-questions/
* https://itanddigital.ru/interviewnet
* https://ru.bitdegree.org/rukovodstvo/chto-takoe-net/
* https://metanit.com/sharp/interview/
* https://ivinsky.livejournal.com/3266.html
* https://itvdn.com/ru/blog/article/150-questions-net-developer

# Учебники

* https://metanit.com/sharp/tutorial/
* https://professorweb.ru/my/csharp/charp_theory/level1/index.php
* http://mycsharp.ru
* https://itproger.com/, https://itproger.com/course/csharp

