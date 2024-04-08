Для  подготовки окружения запустим скрипт: 

`prepare.sh`{{execute}}

скрипт выполняет следующее:
- выполняет деплой Gravitee apim
- выполняет деплой httpbin

Ожидаем 2-3 мин, пока все компоненты будут успешно инсталлированы. 

### Проверка окружения
получим список запущенных подов в кластере и убедимся что у всех статус Running

`kubectl get po -A  | grep -v Complete`{{execute}}


На этом настройка окружения успешно завершена.