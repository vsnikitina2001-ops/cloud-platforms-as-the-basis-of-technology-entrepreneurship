University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FTMI](https://ftmi.itmo.ru/)\
Course: [Введение в веб технологии](https://itmo-ict-faculty.github.io/introduction-in-web-tech/)\
Year: 2025/2026\
Group: U4125\
Author: Borisova Valeriya Sergeevna\
Lab: Lab3\
Date of create: 01.05.2026\
Date of finished:


## 1. Создание bucket

В Google Cloud Platform открыла раздел **Cloud Storage** и создала новый bucket со стандартными настройками.

<img width="1188" height="534" alt="Снимок экрана 2026-05-08 в 02 33 20" src="https://github.com/user-attachments/assets/1285bb72-0bd0-45be-8c52-1ea72b1dc3e3" />

---

## 2. Загрузка файлов

Загрузила 4 изображения в созданный bucket через функцию **Upload files**.

<img width="1188" height="382" alt="Снимок экрана 2026-05-08 в 02 38 58" src="https://github.com/user-attachments/assets/159bc245-6ad7-4459-a349-903ffe33ad2b" />

---

## 3. Создание папки и перемещение файлов

Создала папку внутри bucket и переместила в неё загруженные изображения.

<img width="1191" height="670" alt="Снимок экрана 2026-05-08 в 02 40 12" src="https://github.com/user-attachments/assets/705b77ef-2b0d-4b63-a1d3-f9791f68d862" />
<img width="1187" height="525" alt="Снимок экрана 2026-05-08 в 02 41 19" src="https://github.com/user-attachments/assets/f83d56d7-08a7-4e93-93d4-0fe209df115c" />

---

## 4. Настройка публичного доступа

Для файлов настроила публичный доступ:
- Principal: `allUsers`
- Role: `Storage Object Viewer`

<img width="1186" height="547" alt="Снимок экрана 2026-05-08 в 02 58 00" src="https://github.com/user-attachments/assets/eb8276bf-c8f4-410f-b357-04ca12a36eef" />

---

## 5. Получение ссылки на файл

Скопировала публичную ссылку на файл через функцию **Copy URL** и проверила доступность файла в браузере.

<img width="1434" height="787" alt="Снимок экрана 2026-05-08 в 02 58 08" src="https://github.com/user-attachments/assets/80d03ef2-a20f-47f9-b1df-33cdebe1aa5a" />
<img width="1434" height="797" alt="Снимок экрана 2026-05-08 в 02 58 26" src="https://github.com/user-attachments/assets/05ee89c8-8586-48fa-a39a-db96294afa5c" />
<img width="1435" height="785" alt="Снимок экрана 2026-05-08 в 02 58 16" src="https://github.com/user-attachments/assets/97a72ee3-8e1a-4159-9176-5d0d1fdb62db" />

---

## 6. Удаление ресурсов

После завершения работы удалила:
- файлы;
- папку;
- bucket.

---

# Вывод

В ходе лабораторной работы изучила работу Cloud Storage в Google Cloud Platform. Освоила создание bucket, загрузку и организацию файлов, настройку публичного доступа и получение ссылок на объекты.
