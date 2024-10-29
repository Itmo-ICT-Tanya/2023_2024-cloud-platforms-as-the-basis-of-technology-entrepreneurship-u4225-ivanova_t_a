#### University: [ITMO University](https://itmo.ru/ru/)
#### Faculty: [FTMI](https://ftmi.itmo.ru/)
#### Course: [Cloud platforms as the basis of technology entrepreneurship]
#### Year: 2023/2024
#### Group: U4225
#### Author: Ivanova Tatyana Aleksandrovna
#### Lab: Lab2
#### Date of create: 28.10.2024
#### Date of finished: 

## Описание
Это вторая лабораторная работа "Исследование Cloud Run"

## Цель работы
Ознакомиться с работой Cloud Run - это управляемая вычислительная платформа, которая позволяет запускать контейнеры непосредственно поверх масштабируемой инфраструктуры Google.

## Ход работы

1. Создала Cloud Run из представленного дефолтного сервиса с минимальным количеством ресурсов.

Первая версия была создана на порту 8080.

Образ контейнера задеплоен:

![image](https://github.com/user-attachments/assets/b4ac46ed-0f3e-4ba4-942d-95e93a06e931)

2. Проанализировала логи:

![image](https://github.com/user-attachments/assets/c20d6c37-2379-48f2-89d9-075e245cd2f3)

В логах можно увидеть служба Cloud Run с именем "hello-ivanovat" была успешно создана в регионе "us-central1" пользователем "tatyana.ivanova02022001@gmail.com " с помощью Google Cloud Console. Далее можно по логам можно увидеть, что служба Cloud Run «hello-ivanovat» принимает запросы на порту 8080, а также можно увидеть информацию об успешно принятых HTTP GET-запросах.

3. Проанализировала метрики:

Среди метрик представлены следующие: количество запросов, задержка запроса, количество экзмепляров контейнера, оплачиваемое время экземпляра контейнера, загрузка ЦП контейнера, использование памяти котнейнера, количество отправленных и полученных байтов, максимальное количество одновременных запросов и задержка запуска контейнера.

Активность на отображаемых графиках метрик происходила за счет того, что обращались к странице с информацией о запуске образа контейнера (см.выше).

![image](https://github.com/user-attachments/assets/3fa1411a-39f5-4b67-a109-fb6045a5a3ac)
![image](https://github.com/user-attachments/assets/f4f9d92a-83ac-410c-ba8f-74dcead5d329)
![image](https://github.com/user-attachments/assets/95d5e760-9d21-4804-a2da-4482dbccc4c2)
![image](https://github.com/user-attachments/assets/0abf8a51-9a45-4397-a5e8-59826db8812e)
![image](https://github.com/user-attachments/assets/68128275-0bf3-44ff-b0d0-609c3428a421)

4. Далее создала еще один образ контейнера на порту 8090

![image](https://github.com/user-attachments/assets/285b201f-ebd0-418d-864f-4c17a3f8f5d3)

6. Проанализировала логи:

![image](https://github.com/user-attachments/assets/2c6cb307-4e3c-4dc7-bf6b-feba7afde313)

В логах можно отметить, что произошло успешное обновление сервиса Cloud Run "ivanova-t" в регионе "us-central1", служба Cloud Run «hello-ivanovat» принимает запросы на порту 8090 и также можно увидеть информацию об успешно принятых HTTP GET-запросах.

7. Проанализировала метрики:
![image](https://github.com/user-attachments/assets/fae03635-cb06-4f9f-8050-c991263b497e)
![image](https://github.com/user-attachments/assets/9076fb0a-568f-4589-9940-f222707d6ef3)
![image](https://github.com/user-attachments/assets/6ccd8a14-500f-4866-842c-8a83f3389186)
![image](https://github.com/user-attachments/assets/d36ae4c7-6b7c-41e7-b878-fea51c05c4bb)
![image](https://github.com/user-attachments/assets/ba4a19f9-f121-4d0c-aa01-1392995582e3)

Можно отметить, что метрики начали изменяться такие, как количество запросов (уменьшение до 0), задержка запроса (рост до 11 ms), количество экзмепляров контейнера (увеличение до одного), оплачиваемое время экземпляра контейнера (уменьшение до 0), количество отправленных и полученных байтов (уменьшение до 0), максимальное количество одновременных запросов (увеличение до 2).

9. Протестировала переключения трафика между версиями:
    
90%/10%:

![image](https://github.com/user-attachments/assets/f2cd9338-3530-471b-abe3-c20be8175728)

Лог, показывающий распределение трафика:

![image](https://github.com/user-attachments/assets/0110bd45-cf02-44c9-8513-d9248d0d843c)

50%/50%:

![image](https://github.com/user-attachments/assets/f50aa61e-2346-415a-b27a-03577f22b856)

Лог, показывающий распределение трафика:

![image](https://github.com/user-attachments/assets/00382d7b-2b80-4b0b-8da9-965b7cbb55b8)

Повторила переключение в таких же пропорциях еще один раз.

Для того, чтобы проследить, как распределяется трафик между версиями, я обращалась к сайту с информацией о запуске контейнера несколько раз, что можно увидеть по логам - GET200 (успешно принятые HTTP GET-запросы):

![image](https://github.com/user-attachments/assets/b636028f-ba59-4cdc-babb-9e31616573e5)

При распределении трафика 90%/10% больше трафика принимает на себя версия на порту 8080, а при распределении трафика 50%/50% обе версии принимают на себя примерно одинаковое количестов трафика.

Это можно отследить с помощью отслеживание метрики "Количество запросов":

Распределение трафика 90%/10%:

![image](https://github.com/user-attachments/assets/fab8577e-f519-4d17-8ca6-85f6413c8872)


Распределение трафика 50%/50% - распределение трафика начинает уравниваться:

![image](https://github.com/user-attachments/assets/4530645a-990c-4b64-890a-4bdc377ef2cf)


10. Удалила за собой все созданные сервисы

## Выводы

Создание разных версий контейнера позволяет распределять нагрузку от трафика и является ключевым аспектом для реализации разных версий приложения или A/B тестирования.

