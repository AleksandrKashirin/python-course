Для  подготовки окружения запустим скрипт: 

`prepare.sh`{{execute}}

скрипт выполняет следующее:
- создает необходимые неймспейсы в kubernetes
- создает файл переменных окружения ~/envs
- выполняет деплой системных компонент OpenFaaS, Gravitee apim, registry
- устанавливает консольную утилиту faas-cli для взаимодействия с OpenFaaS из командной строки
- скачивает темплейт для создания функций на языке python в root/template
- устанавливает gravitee apim

Ожидаем 3-5 мин, пока все компоненты будут успешно инсталлированы. 

Далее, для установки переменных окружения используем созданный файл:

`source ~/envs`{{execute}}
### Проверка окружения
получим список запущенных подов в кластере и убедимся что у всех статус Running

`kubectl get po -A  | grep -v Complete`{{execute}}

Проверим доступ из консольного клиента к OpenFaaS 

`faas-cli list -v`{{execute}}

т.к. ни одной функции мы еще не создали, вывод будет следующий:
```
Function                        Image                                           Invocations     Replicas        CreatedAt
```
На этом настройка окружения успешно завершена. Далее попробуем запустить свою первую serverless функцию.