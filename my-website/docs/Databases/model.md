---
title: ERD
sidebar_position: 1
---

# Модель данных

import Drawio from '@theme/Drawio'
import diagram from '!!raw-loader!./db_is.drawio';

<Drawio content={diagram} editable={false} />


## Doctor

| Название | Тип     | Описание              |
| -------- | ------- | --------------------- |
| id       | int     | Идентификатор доктора |
| patient_id       | int     | Идентификатор пациента у доктора |
| full_name     | varchar | ФИО Доктора           |
| gender   | char    | Пол врача        |
| photo    | varbinary | Фото врача     |
| position   | varchar | Должность врача|
| category    | varchar | Категория врача|

## Patient

| Название | Тип     | Описание              |
| -------- | ------- | --------------------- |
| id       | int     | Идентификатор пациента |
| diagnosis_id     | int | Идентификатор диагноза у пациента        |
| full_name   | varchar    | ФИО пациента   |
| birthday    | date | Дата рождения пациента                |
| photo   | varbinary | Фото пациента                 |
| gender    | char | Пол пациента                 |

## Diagnosis

| Название | Тип     | Описание              |
| -------- | ------- | --------------------- |
| id       | int     | Идентификатор дигноза |
| name   | varchar    | Статус питомца        |
| date_first    | date | Фото                  |
| date_change   | date | Фото                  |
| description    | varchar | Фото                  |
| photo    | binary | Фото                  |
