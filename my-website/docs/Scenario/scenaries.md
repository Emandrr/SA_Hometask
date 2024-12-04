---
title: Схемы информационной системы
sidebar_position: 1
---
# Sequence Diagram Информационной Системы

```plantuml

@startuml
actor "Пациент" as c
participant "Информационная система" as s
database "БД Информационной системы" as db2

c -> s: Вход в информационную систему
activate s
s -> db2: Запрос данных
db2 -> s: Результат запроса данных
alt Данные найдены
s -> c: Отправка данных пользователю
else Нет данных
s -> c: Уведомление об отсутствии данных
end
deactivate s
@enduml
```

## Описание алгоритма

1. **Owner** отправляет запрос: `POST /pet` с данными питомца.
2. **System** проверяет данные:
   - Если данные корректны:
     - **System** сохраняет данные в **Database**.
     - **System** отправляет **Owner**: `200 OK`.
   - Если данные некорректны:
     - **System** отправляет **Owner**: `405 invalid input`.

# Use Case Diagram Информационной Системы

```plantuml

@startuml
actor Пациент as p
actor Врач as c

package Информационная_система {
usecase "Просмотреть медицинскую карту пациента" as UC1
usecase "Найти пациента" as UC2
usecase "Добавить медицинскую карту пациента" as UC3
usecase "Редактировать медицинскую карту пациента" as UC4
usecase "Просмотреть свои данные" as UC5
}
p -> UC5
UC1 <-- UC2
UC1 <|-- UC3: extend
UC1 <|-- UC4: extend
c ---> UC2
@enduml

```


