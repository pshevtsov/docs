# Метод create
Создает ключ доступа для указанного сервисного аккаунта.
 

 
## HTTP-запрос
`POST /iam/aws-compatibility/v1/accessKeys`
 
## Параметры в теле запроса {#body_params}
 
```json 
 {
  "serviceAccountId": "string",
  "description": "string"
}
```

 
Поле | Описание
--- | ---
serviceAccountId | **string**<br><p>Идентификатор сервисного аккаунта для которого создается ключ доступа. Чтобы получить идентификатор сервисного аккаунта, используйте запрос <a href="/docs/iam/api-ref/ServiceAccount/list">list</a>. Если <a href="/docs/iam/api-ref/AccessKey/create#body_params">serviceAccountId</a> не указан, то используется идентификатор субъекта, который сделал запрос.</p> <p>Максимальная длина — 50 символов.</p> 
description | **string**<br><p>Описание ключа доступа. Длина описания должна быть от 0 до 256 символов.</p> <p>Максимальная длина — 256 символов.</p> 
 
## Ответ {#responses}
**HTTP Code: 200 - OK**


 
Поле | Описание
--- | ---
accessKey | **object**<br><p>Ресурс AccessKey.</p> <p>Ресурс AccessKey — статический ключ доступа. Используется для авторизации в HTTP API, совместимом с Amazon S3.</p> 
accessKey.<br>id | **string**<br><p>Только для вывода. Идентификатор ресурса AccessKey. Используется для управления учетными данными: идентификатором ключа доступа и секретным ключом доступа.</p> 
accessKey.<br>serviceAccountId | **string**<br><p>Идентификатор сервисного аккаунта, которому принадлежит ключ доступа.</p> 
accessKey.<br>createdAt | **string** (date-time)<br><p>Только для вывода. Время создания ресурса в формате в <a href="https://www.ietf.org/rfc/rfc3339.txt">RFC3339</a>.</p> 
accessKey.<br>description | **string**<br><p>Описание ключа доступа. Длина описания должна быть от 0 до 256 символов.</p> 
accessKey.<br>keyId | **string**<br><p>Только для вывода. Идентификатор ключа доступа. Ключ совместим с сервисами AWS.</p> 
secret | **string**<br><p>Секретный ключ доступа. Ключ совместим с сервисами AWS.</p> 