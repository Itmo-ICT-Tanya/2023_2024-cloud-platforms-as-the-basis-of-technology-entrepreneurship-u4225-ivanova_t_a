#### University: [ITMO University](https://itmo.ru/ru/)
#### Faculty: [FTMI](https://ftmi.itmo.ru/)
#### Course: [Cloud platforms as the basis of technology entrepreneurship]
#### Year: 2023/2024
#### Group: U4225
#### Author: Ivanova Tatyana Aleksandrovna
#### Lab: Lab3
#### Date of create: 29.10.2024
#### Date of finished: 

## Описание
Это третья лабораторная работа Исследование Cloud Storage

## Цель работы
Ознакомиться с основными понятиями и принципами работы облачного хранилища, изучат различные модели хранения данных (блок, файл, объектное хранилище), познакомятся с основными сервисами и функционалом, предоставляемым облачными хранилищами.

## Ход работы

1. Выбрала существующий проект, в котором есть соответствующие разрешения
   
2. Создала Cloud Storage bucket - как папка в Google Cloud Storage (GCS), служит для организации и хранения объектов в GCS. 

![image](https://github.com/user-attachments/assets/aeaf2c00-b6fd-4b10-86bf-9a8037fdde96)

3. Загрузила 3 изображения в Cloud Storage bucket
   
![image](https://github.com/user-attachments/assets/ac6534dd-9aa0-4edc-9ca6-3fe1ee7a0f29)

4. Создала папку с названием "Animals" и переместила файлы туда в пределах бакета (с помощью Move)

![image](https://github.com/user-attachments/assets/29eeaf86-e8bc-451b-ab16-aed3aa600fc2)

![image](https://github.com/user-attachments/assets/95850041-8bbb-4413-93be-a7e37620de12)

5. Настроила публичный доступ для файлов в настройках приватности

![image](https://github.com/user-attachments/assets/b50a3ae8-5dc4-447c-962d-652ad29463aa)

6. Создать ссылку на файлы через контекстное меню файла

https://storage.cloud.google.com/ivanovat-bucket/Animals/%D0%BA%D0%B0%D0%BF%D0%B8%D0%B1%D0%B0%D1%80%D0%B0.jpg
https://storage.cloud.google.com/ivanovat-bucket/Animals/%D0%BA%D0%BE%D1%80%D0%B6%D0%B8%D0%BA.jpg
https://storage.cloud.google.com/ivanovat-bucket/Animals/%D0%BA%D0%BE%D1%82%D0%B8%D0%BA.jpg

Проверила работоспособность ссылок:
![image](https://github.com/user-attachments/assets/d4dc6cf9-3183-4b7c-9d68-1f0d62548902)
![image](https://github.com/user-attachments/assets/c3eeeb5e-2ac4-4884-90d0-dc6aa82b70ac)
![image](https://github.com/user-attachments/assets/615b62ef-5f3f-4579-9b5b-b7862289b88c)

7. Удалила за собой все созданные сервисы

## Выводы
В ходе лабораторной работы был изучен Google Cloud Storage (GCS) — это облачное хранилище объектов от Google Cloud Platform, предоставляющее безопасный, масштабируемый и долговечный способ хранения данных. В этом хранилище можно хранить файлы в бакетах и с ними можно производить различные действия: загрузка, перемещение в папки, предоставление доступа, создание ссылка на файлы.
