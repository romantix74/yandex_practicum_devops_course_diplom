# Momo Store aka Пельменная №2

<img width="900" alt="image" src="https://user-images.githubusercontent.com/9394918/167876466-2c530828-d658-4efe-9064-825626cc6db5.png">

# Инфраструктура для проекта
Деплоим используя [репозиторий](https://gitlab.praktikum-services.ru/std-022-024/momo-infrastructure)

## Frontend

```bash
npm install
NODE_ENV=production VUE_APP_API_URL=http://localhost:8081 npm run serve
```

## Backend

```bash
go run ./cmd/api
go test -v ./... 
```


## Доменное имя

Куплен домен momo-store-std-022-024.ru  на reg.ru. Указаны адреса серверов имен Yandex Cloud в DNS-записях  регистратора:

- ns1.yandexcloud.net
- ns2.yandexcloud.net