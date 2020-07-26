#Результат
Образ приложения: `ovgusev/actuator-app`
Запуск minikube: `minikube start --vm-driver=hyperv`
Включение ingress аддона: `minikube addons enable ingress`
Запуск приложения в default namespace: `kubectl apply -f .`
url для проверки: `http://arch.homework/otusapp/ovgusev/health`
---
#Задание

Основы работы с Kubernetes (часть 2)
Создать минимальный сервис, который
1) отвечает на порту 8000
2) имеет http-метод
GET /health/
RESPONSE: {"status": "OK"}

Cобрать локально образ приложения в докер.
Запушить образ в dockerhub

Написать манифесты для деплоя в k8s для этого сервиса.

Манифесты должны описывать сущности Deployment, Service, Ingress.
В Deployment обязательно должны быть указаны Liveness, Readiness пробы.
Количество реплик должно быть не меньше 2. Image контейнера должен быть указан с Dockerhub.

В Ingress-е должно быть правило, которое форвардит все запросы с /otusapp/{student name}/* на сервис с rewrite-ом пути. Где {student name} - это имя студента.

Хост в ингрессе должен быть arch.homework. В итоге после применения манифестов GET запрос на http://arch.homework/otusapp/{student name}/health должен отдавать {“status”: “OK”}.

На выходе предоставить
0) ссылку на github c манифестами. Манифесты должны лежать в одной директории, так чтобы можно было их все применить одной командой kubectl apply -f .
1) url, по которому можно будет получить ответ от сервиса (либо тест в postmanе)
