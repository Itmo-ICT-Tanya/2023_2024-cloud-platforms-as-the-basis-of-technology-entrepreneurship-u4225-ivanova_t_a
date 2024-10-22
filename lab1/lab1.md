University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FTMI](https://ftmi.itmo.ru/)
Course: [Cloud platforms as the basis of technology entrepreneurship]
Year: 2023/2024
Group: U4225
Author: Ivanova Tatyana Aleksandrovna
Lab: Lab1
Date of create: 21.10.2024
Date of finished: 

## Описание
Это первая лабораторная работа "Обзор Google Cloud и исследование основных сервисов."

## Цель работы
Ознакомиться с основными возможностями и преимуществами облачной платформы Google Cloud.

## Ход работы

### Вам необходимо заполнить гугл форму, приложив свою Gmail почту, чтобы вам выдали доступы к Google Cloud.
Сделано

### Зайдите в вкладку IAM, создайте service account с ролью Storage Admin.
![image](https://github.com/user-attachments/assets/a586ef43-162e-444d-9fa3-d09cfe92c25e)

### Создать минимальный compute engine (виртуальную машину) с Machine type e2-micro в режиме spot.
![image](https://github.com/user-attachments/assets/65e7b924-da5e-4cb3-a74e-4eea9cff3aa3)

### С помощью утилиты gsutils найдите бакет lab1-bucket-itmo и скопируйте 3 файла в локальную папку на VM. Используя команду ls -lah отобразите что эти файлы хранятся у вас на VM.

![image](https://github.com/user-attachments/assets/8e90f4dc-938b-4463-a769-063a4dc34157)


### Поменяйте права доступа для вашего service account с Storage Admin на Compute Viewer, попробуйте повторить пункт с копированием данных, сделать выводы.

![image](https://github.com/user-attachments/assets/1115cd73-f612-44b3-8584-f3b709c54eea)
![image](https://github.com/user-attachments/assets/9566d25d-4a3d-44bf-bfd7-92e277ffbe26)

## Выводы: 
роль Storage Admin предоставляет полный контроль над контейнерами, папками, управляемыми папками и объектами, а Compute Viewer дает доступ только для чтения для получения и просмотра информации обо всех ресурсах Compute Engine, включая экземпляры, диски и брандмауэры и позволяет получать и просматривать информацию о дисках, образах и снимках, но не позволяет читать хранящиеся на них данные.
