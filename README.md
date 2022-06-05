**Развертывание и URL**
   - Предварительно создание .env:
```shell
  cp .env.sample .env
  cp tests/functional/.env.sample tests/functional/.env
```
   - Запуск сервисов через docker-compose:
```shell
 docker-compose up 
```
   - Локальное функциональное тестирование (при запущенных сервисах):
```shell
  pytest tests/functional
```
   - Функциональное тестирование через docker-compose (при запущенных сервисах)
```shell
 docker-compose -f ./tests/functional/docker-compose.functional-tests-in-docker.yml up 
```

- Ссылки на сервисы после развертывания:
    - OpenAPI swagger UI: http://localhost:8000/api/openapi
    - Django admin: http://localhost:8000/admin/  (user=admin, password=admin)
    - Django api: http://localhost:9000/api/v1/movies  (+/uuid)
    - FastAPI api films: http://localhost:8000/api/v1/films (+/uuid)
    - FastAPI api genres: http://localhost:8000/api/v1/genres (+/uuid)
    - FastAPI api persons: http://localhost:8000/api/v1/persons (+/uuid)
    - Elasticsearch (для целей разработки): http://localhost:9200/
    - Redis (для целей разработки, двоичный): localhost:6379 
    
## Несколько ремарок по ходу решения
- есть немного "халтурки" (и я знаю, где именно). Но в целом, скорее
  интересует внешняя оценка на предмет "сильного упущения в чем-то", т.к. "просто 
  реализовать функциональность" - это не проблема для работы данного уровня.
- Для улучшения качества проекта и качества кода, следует написать больше тестов,
  так же добавить проверку с помощью линтеров (предпочтительно flake8 и его плагины).
  Плюс хорошо бы сделать проект более типизированным и понятным (так же добавить проверку mypy)
- К проекту 07.06 будет добавлена авторизация и скрипты для раскатки в YandexCloud
