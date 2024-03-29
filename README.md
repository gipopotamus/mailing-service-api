# Сервис уведомлений

Сервис разработан на django rest framework, celery + redis


## Установка проекта с помощью docker-compose


1. Склонировать репозиторий с Github
```
git clone git@github.com:gipopotamus/mailing-service.git
```
2. Перейти в директорию проекта
3. Запустить контейнеры 
``` 
docker-compose up -d
 ```
4. Запуск тестов
```
docker exec -it web python manage.py test
```
6. Остановка работы контейнеров 
```
docker-compose stop
```
***
```http://0.0.0.0:8000/api/``` - api проекта

```http://0.0.0.0:8000/api/clients/``` - клиенты

```http://0.0.0.0:8000/api/mailings/``` - рассылки

```http://0.0.0.0:8000/api/mailings/statistics/``` - общая статистика по всем рассылкам

```http://0.0.0.0:8000/api/mailings/<id>/message_statistics/``` - детальная статистика по конкретной рассылке

```http://0.0.0.0:8000/api/mailings/<id>/start_mailing``` - запуск рассылки

```http://0.0.0.0:8000/docs/``` - docs проекта

***

**Техзадание:** 
[https://www.craft.do/s/n6OVYFVUpq0o6L](https://www.craft.do/s/n6OVYFVUpq0o6L)

## Задача

<p>Необходимо разработать сервис управления рассылками API администрирования и получения статистики</p>

## Описание
<ul>
<li>Необходимо реализовать методы создания новой рассылки, просмотра созданных и получения статистики по выполненным рассылкам.</li>
<li>Реализовать сам сервис отправки уведомлений на внешнее API.</li>
<li>Опционально вы можете выбрать любое количество дополнительных пунктов описанных после основного.</li>
</ul>

<p>Для успешного принятия задания как выполненного достаточно корректной и рабочей реализации требований по основной части, но дополнительные пункты помогут вам продемонстрировать ваши навыки в смежных технологиях.</p>


## Дополнительные задания
<ol>
<li>организовать тестирование написанного кода</li>
<li>подготовить docker-compose для запуска всех сервисов проекта одной командой</li>
<li>сделать так, чтобы по адресу <i> /docs/ </i> открывалась страница со Swagger UI и в нём отображалось описание разработанного API. </li>
<li>удаленный сервис может быть недоступен, долго отвечать на запросы или выдавать некорректные ответы. Необходимо организовать обработку ошибок и откладывание запросов при неуспехе для последующей повторной отправки. Задержки в работе внешнего сервиса никак не должны оказывать влияние на работу сервиса рассылок.</li>

</ol>
