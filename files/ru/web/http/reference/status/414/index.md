---
title: 414 URI Too Long
slug: Web/HTTP/Reference/Status/414
---

Код состояния HTTP **`414 URI Too Long`** указывает, что URI, запрошенный клиентом, длиннее, чем сервер готов интерпретировать.

Есть несколько редких условий, когда это может произойти:

- Когда клиент неправильно конвертировал {{HTTPMethod("POST")}} запрос в {{HTTPMethod ("GET")}} запрос с длинной информацией запроса,
- Когда клиент спустился в цикл перенаправления (например, перенаправленный префикс URI, который указывает на суффикс самого себя),,
- Или когда сервер подвергается атаке со стороны клиента, пытающегося использовать потенциальные дыры в безопасности.

## Статус

```
414 URI Too Long
```

## Спецификации

| Спецификации                                   | Название                                                      |
| ---------------------------------------------- | ------------------------------------------------------------- |
| {{RFC("7231", "414 URI Too Long" , "6.5.12")}} | Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content |

## Смотрите также

- {{Glossary("URI")}}
