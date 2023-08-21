### Этот проект создан для демонстарции знаний и умений студента IT школы TeachMeSkills по направлению DevOps инженер
 
### Цели
##### 1. Инфраструктура как код
##### 2. Определить всю инфраструктуру как текстовые файлы 
##### 3. Автоматизировать развертывание и подготовку
##### 4. Настроить мониторинг приложения и компонентов системы в целом
##### 5. Рассылка уведомления при старте и финише деплоя, а так же при недоступности приложения.
##### 6. Должно быть просто перенести инфраструктуру с одного сервера на другой, если возникнет такая необходимость

### Инструменты
#### Ansible
```sh
Ansible — одно из многих решений для управления конфигурацией. Мне он больше всего нравится 
за безагентный подход и элегантные определения. Однако из-за своего процедурного стиля
постановки задач он может стать довольно громоздким для управления существующими серверами 
в конкретных случаях. Из-за этого и потому, что я хотел бы стремиться к более неизменной 
инфраструктуре, этот проект будет использовать ее только в качестве инструмента подготовки.
```
#### Docker 
```sh
Docker - это открытая платформа для разработки, доставки и эксплуатации приложений. 
Docker разработан для более быстрого выкладывания ваших приложений. С помощью docker вы 
можете отделить ваше приложение от вашей инфраструктуры и обращаться с инфраструктурой 
как управляемым приложением. Docker помогает выкладывать ваш код быстрее, быстрее тестировать, 
быстрее выкладывать приложения и уменьшить время между написанием кода и запуска кода. Docker 
делает это с помощью легковесной платформы контейнерной виртуализации, используя процессы и
 утилиты, которые помогают управлять и выкладывать ваши приложения.
```
#### SystemD
```sh
Systemd — менеджер системы и служб для Linux, совместимый со скриптами инициализации SysV и LSB. 
Systemd обеспечивает возможности агрессивной параллелизации и много всего прочего. Огромный 
монстр с множеством возможностей, гибкими настройками и мегабайтами документации. Но что делать, 
если стоит задача быстро-быстро, вот прямо вчера, сделать автозапуск некоего сервиса? Давайте 
выжмем из документации минимально необходимый набор информации для создания простых старт-стоп 
скриптов. Systemd запускает сервисы описанные в его конфигурации. Конфигурация состоит из 
множества файлов, которые по-модному называют юнитами.
```
#### Grafana
```sh
Grafana — это платформа с открытым исходным кодом для визуализации, мониторинга и анализа 
данных. Этот инструмент, в сочетании с Graylog, — часть нашей двухсторонней системы мониторинга
поведения пользователей и производительности системы. Grafana позволяет пользователям создавать 
дашборды с панелями, каждая из которых отображает определенные показатели в течение 
установленного периода времени. Каждый дашборд универсален, поэтому его можно настроить для 
конкретного проекта или с учетом любых потребностей разработки и/или бизнеса.
```
#### Prometheus
```sh
Prometheus — это база данных временных рядов. Но Prometheus — не просто база данных временных
рядов. К нему можно присоединить целую экосистему инструментов, чтобы расширить функционал. 
Prometheus мониторит самые разные системы: серверы, базы данных, отдельные виртуальные машины, 
да почти что угодно.
```
#### Alertmanager
```sh
Alertmanager — это компонент системы мониторинга Prometheus, который обрабатывает оповещения, 
группирует их и отправляет получателю на электронную почту, в Telegram или Slack. Компонент 
формирует уведомления на основе правил, которые заданы в конфигурационном файле.
```
#### Black-box exporter
```sh
Blackbox exporter 一 инструмент, предназначенный для мониторинга внешних систем и сервисов. Этот 
инструмент используется для проверки доступности и работоспособности этих систем через различные 
протоколы HTTP, DNS, TCP, ICMP и другие.
```
#### CadVizor
```sh
cAdvisor будет собирать метрики хостов и контейнеров. Он устанавливается в виде docker-образа c 
подключенным в виде общего тома сокетом docker и корневой файловой системой на хосте. cAdvisor 
может записывать собираемые метрики в несколько видов баз данных временных рядов (time-series 
database), включая InfluxDB, Prometheus и т. д. У него даже есть веб-интерфейс, в котором по 
собранным данным строятся графики.
```
### Jenkins
```sh
Jenkins – не просто инструмент CI/CD. Это Framework, потому что он:
	Гибок и расширяем. 
	Jenkins — опенсорсный проект с множеством внешних расширений.
	
	Минимален из коробки. 
	У Jenkins есть контроллер. Вы можете подключить к нему несколько слоев 
	и уже на этом сетапе собрать минимальный пайплайн, который позволит 
	автоматизировать работу по обновлению сервисов.
	
	Требует настройки. 
	Jenkins — один из кубиков, с помощью которого можно построить большую 
	систему автоматизации. Но прежде чем сделать что-то, его придётся настроить.
Jenkins — это Java-приложение. У него есть контроллер или Master Mode — управляющий центр, 
который занимается планированием задач. Он запускает задачи согласно установленному 
расписанию на слэйвах, которые вы к нему прикрепили. Помимо этого контроллер хранит логи 
наших задач. Вся история хранится только на Master Mode, поэтому важно помнить о настройке 
правильной ротации логов.
```
### GitHub
```sh
GitHub — это сервис для совместной разработки и хостинга проектов. C помощью GitHub над кодом
проекта может работать неограниченное количество программистов из любых точек мира. В GitHub 
есть система контроля (управления) версий Git: сервис позволяет просматривать и контролировать 
любые изменения кода любым разработчиком и возвращаться к состоянию до изменений.
```

### 
