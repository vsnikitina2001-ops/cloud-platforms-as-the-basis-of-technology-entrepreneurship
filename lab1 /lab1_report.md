University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FTMI](https://ftmi.itmo.ru/)\
Course: [Введение в веб технологии](https://itmo-ict-faculty.github.io/introduction-in-web-tech/)\
Year: 2025/2026\
Group: U4125\
Author: Borisova Valeriya Sergeevna\
Lab: Lab1\
Date of create: 01.05.2026\
Date of finished:


### 1. Создание Service Account  
В разделе **IAM & Admin → Service Accounts** был создан сервисный аккаунт:  

**Название:** `vborisova-sa-lab1`  
**Роль:** Storage Admin  

<img width="1439" height="750" alt="Снимок экрана 2026-05-05 в 18 32 15" src="https://github.com/user-attachments/assets/327aad82-b099-4e5a-95ee-1de6d5147c95" />
<img width="580" height="566" alt="Снимок экрана 2026-05-05 в 18 34 15" src="https://github.com/user-attachments/assets/fa6f289a-42ee-4d95-b3c2-701bcfe395cb" />

---

### 2. Создание виртуальной машины  

В сервисе **Compute Engine** создана виртуальная машина со следующими параметрами:
<img width="768" height="313" alt="Снимок экрана 2026-05-05 в 18 38 34" src="https://github.com/user-attachments/assets/edf5a923-bcc0-4a0b-8d80-8e2c0158d497" />

- **Название:** `vborisova-vm-lab1`  
- **Тип:** e2-micro  
- **Режим:** Spot  

<img width="1390" height="289" alt="Снимок экрана 2026-05-05 в 18 38 09" src="https://github.com/user-attachments/assets/36accaca-9b0b-4b9e-9cea-766c41decc7b" />

---

### 3. Подключение к VM  

Подключение выполнено через SSH из веб-консоли GCP.  

---

### 4. Копирование файлов из Cloud Storage  

С помощью команды:
gcloud storage cp gs://lab1-bucket-itmo/* .

были скопированы файлы из bucket в локальную директорию VM.

Проверка выполнена командой:
ls -lah

Файлы успешно отображаются в системе.

<img width="887" height="417" alt="Снимок экрана 2026-05-05 в 18 42 20" src="https://github.com/user-attachments/assets/96b01779-37cd-421a-9c4c-643ca585e692" />

---

### 5. Изменение роли Service Account  

Роль сервисного аккаунта была изменена:

- **Было:** Storage Admin  
- **Стало:** Compute Viewer  

<img width="1436" height="710" alt="Снимок экрана 2026-05-05 в 19 37 13" src="https://github.com/user-attachments/assets/5da4e7ea-5afc-4fa1-b4bc-65f39efc508a" />

---

### 6. Повторная проверка доступа  

После изменения роли повторно выполнена команда:
gcloud storage cp gs://lab1-bucket-itmo/* .

Файлы были успешно скопированы, несмотря на отсутствие роли доступа к Cloud Storage.

<img width="745" height="182" alt="Снимок экрана 2026-05-05 в 19 47 08" src="https://github.com/user-attachments/assets/885309fb-c84a-431a-bcac-612c28b13004" />

---

## Вывод  

В ходе лабораторной работы было установлено, что:

- доступ к ресурсам в Google Cloud управляется через IAM роли  
- роль **Storage Admin** предоставляет полный доступ к Cloud Storage  
- роль **Compute Viewer** не предназначена для работы с Cloud Storage  

Однако после смены роли доступ к bucket сохранился. Это связано с тем, что в Google Cloud используется многоуровневая модель управления доступом, включающая:

- IAM роли  
- access scopes виртуальной машины  
- политики доступа на уровне проекта  

Таким образом, доступ к Cloud Storage может сохраняться даже при изменении роли, если остаются дополнительные разрешения.
