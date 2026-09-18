# devops-course-2026
ОТЧЁТ ПО ПРАКТИКЕ №3

VCS Хостинг и Контейнеры

Студент: Глущенко Георгий
Группа: ЭФБО-18-24
Дата: 18.09.2026
ОС: macOS (Apple M4)

Цель работы

Изучить работу с удалённым репозиторием (GitHub) и основы контейнеризации (Docker).

Что было сделано

1. VCS Хостинг (GitHub)

Проверил SSH-подключение: ssh -T git@github.com 
Создал ветку feature/goals:

bash
git checkout -b feature/goals
Создал файл goals.md с целями на семестр
Закоммитил и запушил ветку:

bash
git add goals.md
git commit -m "Add goals.md with semester goals"
git push origin feature/goals
Создал Pull Request на GitHub и смержил в main
Вернулся в main и подтянул изменения:

bash
git checkout main
git pull origin main
2. Docker (Контейнеры)

Установил Colima и Docker (альтернатива Docker Desktop для Mac):

bash
brew install colima docker
Запустил Colima:

bash
colima start
Проверил работу Docker:

bash
docker run hello-world
Запустил контейнер с Nginx:

bash
docker run -d -p 8081:80 --name my-nginx nginx
Проверил работу:

bash
docker ps
Открыл в браузере: http://localhost:8081 — страница Nginx 
Посмотрел логи:

bash
docker logs my-nginx
Результаты:

Задание	Статус
SSH-подключение к GitHub	
Создание ветки feature/goals	
Создание goals.md	
Pull Request и merge	
Установка Docker	
Запуск контейнера Nginx	
Сайт на http://localhost:8081
Артефакты:

Репозиторий: https://github.com/glushchenko-git/devops-course-2026
Ветка: feature/goals
Контейнер: my-nginx на порту 8081
Ответы на вопросы:

VCS Хостинг — платформа для размещения Git-репозиториев (GitHub, GitLab).
Pull Request — запрос на слияние изменений из одной ветки в другую.
Docker — платформа для контейнеризации приложений.
Разница контейнера и виртуалки: контейнер легче, использует ядро хоста, запускается за секунды.
docker run -d -p 8081:80 --name my-nginx nginx — запускает контейнер с Nginx в фоне, пробрасывает порт 8081 хоста на 80 контейнера.
Образ — шаблон для создания контейнера.
Colima — бесплатная альтернатива Docker Desktop для Mac.
Логи — показывают, что происходит внутри контейнера (запросы, ошибки).


nano /opt/homebrew/etc/nginx/nginx.conf
nano ~/Sites/my-site/index.html
nano /opt/homebrew/etc/nginx/servers/my-site.conf
curl -I http://localhost:8080