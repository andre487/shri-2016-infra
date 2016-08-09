---

layout: default

---

# &nbsp;

<img src="pictures/hand.png" height="100%">

## **{{ site.presentation.title }}** {#cover}

<div class="info">
	<p class="author">{{ site.author.name }}</p>
</div>

## Инфраструктура

<center>
  <img src="pictures/roads.jpg">
</center>

## История проекта

![](pictures/floppy.jpg){:.right-image}

Один стартап, магазин дискет

## История проекта

### Стадия 1

<img src="pictures/story-01.jpg" class="right-image" style="width: 400px; height: auto">

  * Один разработчик
  * Один сервер
  * Код в репозитории на GitHub

## История проекта

### Стадия 1

  * `npm test`
  * `git merge feature && git push origin master`
  * `ssh floppy.shop`
  * `git pull origin master`
  * `make && make install`

## История проекта

### Стадия 2

<img src="pictures/story-02.1.jpg" class="right-image" style="width: 400px; height: auto">

Нужно больше фич. Добавляются разработчики

  * Каждому нужно настраивать окружение
  * Никто не должен забывать про тесты
  * Нужно договариваться о деплое

## История проекта

### Стадия 2

<img src="pictures/story-02.2.jpg" class="right-image" style="width: 400px; height: auto">

  * Vagrant – виртуальные окружения
  * Merge только через пулл-реквесты
  * Код-ревью пулл-реквестов
  * Continuous Integration – проверки, тесты
  * Continuous Deployment

## История проекта

### Стадия 3

<img src="pictures/story-03.1.jpg" class="right-image" style="width: 400px; height: auto">

Нагрузка выросла

Единственный сервер не справляется

## История проекта

### Стадия 3

<img src="pictures/story-03.2.jpg" class="right-image" style="width: 400px; height: auto">

Добавили 4 сервера

В скрипте деплоя операция в цикле

## История проекта

### Стадия 4

<img src="pictures/story-04.1.jpg" class="right-image" style="width: 400px; height: auto">

Печаль-беда, откатываем релиз!

О_о

  * `ssh serv1.floppy.shop`
  * `git checkout 4f230ff`
  * `make && make install`

И это на всех серверах

## История проекта

### Стадия 4

<img src="pictures/story-04.2.jpg" class="right-image" style="width: 400px; height: auto">

Автоматизация отката релиза

Версионирование релизов

## История проекта

### Стадия 5

<img src="pictures/story-05.1.jpg" class="right-image" style="width: 400px; height: auto">

Слушайте, а у нас 2 сервера лежат уже 3 дня…

## История проекта

### Стадия 5

<img src="pictures/story-05.2.jpg" class="right-image" style="width: 400px; height: auto">

Мониторинг с оповещениями

## И жили они долго и счастливо
{:.screen-shot}

<center>
  <img src="pictures/story-ending.jpg" height="540">
</center>

## &nbsp;
{:.section}

### Задачи инфраструктуры

## Задачи инфраструктуры

  * Хостинг
  * Инструментарий разработки
  * Корректная интеграция изменений
  * Быстрая доставка фич
  * Релизный цикл с возможностью отката
  * Мониторинг здоровья сервиса

## &nbsp;
{:.section}

### Хостинг

## Хостинг

  * Реальное железо
  * Облачные платформы:
    * Infrastructure-as-a-Service – низкий уровень: машины, сети
    * Platform-as-a-Service – высокий уровень: приложения, функции

## &nbsp;
{:.section}

### Инструментарий разработки

## Инструментарий разработки

Разработчикам нужно совместно работать над кодом,
нужно выполнять этот код

  * Система и хостинг контроля версий:
    * Git – GitHub, BitBucket, GitLab
    * Mercurial – BitBucket
  * Воссоздаваемое окружение
    * Vagrant
    * Otto
    * Docker Compose
  * Многое других направлений, тысячи их

## &nbsp;
{:.section}

### Интеграция изменений

## Интеграция изменений

Нужно понять, что изменения не вносят багов,
прежде чем вливать в основную ветку

  * Continuous Integration
    * Сборка
    * Автоматизированные тесты
    * Дополнение ручным тестированием:
      * Выкладка проекта на тестовые сервера
      * Ручное тестирование
  * Continuous Deployment – дополнение выкладкой в бой

## Интеграция изменений

<table style="text-align: center">
  <tr>
    <td style="vertical-align: middle"><img src="pictures/travis-ci.png" width="120"></td>
    <td style="vertical-align: middle"><img src="pictures/jenkins.png" width="120"></td>
    <td style="vertical-align: middle"><img src="pictures/teamcity.jpg" width="120"></td>
  </tr>
  <tr style="padding: 10px !important">
    <td>Travis CI</td>
    <td>Jenkins</td>
    <td>TeamCity</td>
  </tr>
</table>

## &nbsp;
{:.section}

### Релизный цикл с возможностью отката

## Релизный цикл с возможностью отката

Версионирование релизов

<center>
  <img src="pictures/git-releases.png" height="450">
</center>

## Релизный цикл с возможностью отката

<img src="pictures/shipit.png" width="400">

[github.com/shipitjs/shipit](https://github.com/shipitjs/shipit)

&nbsp;
&nbsp;

  * В проекте `shipitfile.js`
  * Деплой: `shipit production deploy`
  * Откат: `shipit production rollback`

## Релизный цикл с возможностью отката

![](pictures/heroku.jpg){:.right-image}

На Heroku – Git для продакшен-кода:

  * `heroku git:remote -a proj-id`
  * `git push heroku master`

## Релизный цикл с возможностью отката

Пакеты операционных систем

<center>
  <img src="pictures/debian.png" width="500">
</center>

## &nbsp;
{:.section}

### Мониторинг проекта

## Мониторинг проекта

  * Проверка доступности сервиса
  * Анализ показателей на предмет аномалий

## Проверка доступности сервиса

<img src="pictures/metrika-logo.jpg" height="80">

[metrika.yandex.ru](https://metrika.yandex.ru)

## Яндекс.Метрика
{:.screen-shot}

<img src="pictures/metrika.png" height="570">

## Проверка доступности сервиса

<img src="pictures/uptime-robot-logo.png">

[uptimerobot.com](https://uptimerobot.com)


## Uptime Robot
{:.screen-shot}

<img src="pictures/uptime-robot.png" height="570">

## Анализ показателей на предмет аномалий

<img src="pictures/okmeter-logo.png" height="70" style="transform: translate(-30px)">

[okmeter.io](https://okmeter.io)

## OkMeter
{:.screen-shot}

<img src="pictures/okmeter.png" height="570">

## OkMeter

<img src="pictures/okmeter-common-1.png" width="800">

## OkMeter

<img src="pictures/okmeter-fs.png" width="900">

## OkMeter

<img src="pictures/okmeter-net.png" width="900">

## OkMeter

<img src="pictures/okmeter-processes.png" width="900">

## OkMeter

<img src="pictures/okmeter-nginx.png" height="520">

## OkMeter

<img src="pictures/okmeter-trigger.png" width="900">

## OkMeter

<img src="pictures/okmeter-contacts.png" height="450">

## &nbsp;
{:.section}

### Заключение

## Инфраструктура

<table>
  <tr>
    <td>Железо, системное ПО</td>
    <td><input type="checkbox" style="vertical-align: middle" checked=""> <label style="vertical-align: middle">Хостинг</label></td>
  </tr>
  <tr>
    <td>Инструментарий разработки</td>
    <td><input type="checkbox" style="vertical-align: middle" checked=""> <label style="vertical-align: middle">GitHub, Vagrant и т. д.</label></td>
  </tr>
  <tr>
    <td>Корректная интеграция изменений</td>
    <td><input type="checkbox" style="vertical-align: middle" checked=""> <label style="vertical-align: middle">Travis CI, Jenkins, TeamCity</label></td>
  </tr>
  <tr>
    <td>Быстрая доставка фич</td>
    <td><input type="checkbox" style="vertical-align: middle" checked=""> <label style="vertical-align: middle">Автотесты, Continuous Deployment</label></td>
  </tr>
  <tr>
    <td>Релизный цикл с возможностью отката</td>
    <td><input type="checkbox" style="vertical-align: middle" checked=""> <label style="vertical-align: middle">ShipIt</label></td>
  </tr>
  <tr>
    <td>Мониторинг здоровья сервиса</td>
    <td><input type="checkbox" style="vertical-align: middle" checked=""> <label style="vertical-align: middle">Яндекс.Метрика, Uptime Robot, OkMeter</label></td>
  </tr>
</table>

## &nbsp;
{:.section}

### Спасибо за внимание!
