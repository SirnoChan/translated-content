---
title: Authorization
slug: Web/HTTP/Reference/Headers/Authorization
---

Заголовок HTTP запроса **`Authorization`** включает в себя данные пользователя для проверки подлинности пользовательского агента с сервером обычно после того, как сервер ответил со статусом {{HTTPStatus("401")}} `Unauthorized` и заголовком {{HTTPHeader("WWW-Authenticate")}}.

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Тип заголовка</th>
      <td>{{Glossary("Request header")}}</td>
    </tr>
    <tr>
      <th scope="row">
        {{Glossary("Forbidden header name", "Запрещённое имя заголовка")}}
      </th>
      <td>Нет</td>
    </tr>
  </tbody>
</table>

## Синтаксис

```
Authorization: <тип> <данные пользователя>
```

## Директивы

- <тип>
  - : [Тип авторизации](/ru/docs/Web/HTTP/Guides/Authentication#authentication_schemes). Общий тип [«Базовая»](/ru/docs/Web/HTTP/Guides/Authentication#basic_authentication_scheme). Остальные типы:
    - [IANA registry of Authentication schemes](https://www.iana.org/assignments/http-authschemes/http-authschemes.xhtml)
    - [Authentification for AWS servers (`AWS4-HMAC-SHA256`)](https://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-auth-using-authorization-header.html)

- <данные пользователя>
  - : Если используется схема авторизации «Базовая», данные пользователя формируются следующим образом:
    - Логин и пароль, разделённые двоеточием (`aladdin:opensesame`).
    - Результирующая строка, закодированная в [base64](/ru/docs/Glossary/Base64) (`YWxhZGRpbjpvcGVuc2VzYW1l`).

    > [!NOTE]
    > Кодировка Base64 не означает шифрование или хэширование! Этот метод так же небезопасен, как и отправка учётных данных в открытом виде (base64 является обратимой кодировкой). Отдавайте предпочтение использованию HTTPS в сочетании с Базовой Авторизацией.

## Примеры

```
Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l
```

Смотрите также [HTTP авторизацию](/ru/docs/Web/HTTP/Authorization) для примеров конфигураций веб-серверов Apache или nginx с защитой вашего сайта паролем с Базовой HTTP авторизацией.

## Спецификации

| Спецификация                            | Заголовок                              |
| --------------------------------------- | -------------------------------------- |
| {{RFC("7235", "Authorization", "4.2")}} | HTTP/1.1: Authentication               |
| {{RFC("7617")}}                         | The 'Basic' HTTP Authentication Scheme |

## Смотрите также

- [HTTP авторизация](/ru/docs/Web/HTTP/Authorization)
- {{HTTPHeader("WWW-Authenticate")}}
- {{HTTPHeader("Proxy-Authorization")}}
- {{HTTPHeader("Proxy-Authenticate")}}
- {{HTTPStatus("401")}}, {{HTTPStatus("403")}}, {{HTTPStatus("407")}}
