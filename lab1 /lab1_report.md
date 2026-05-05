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

*(Скриншот 1 — создание service account)*  

---

### 2. Создание виртуальной машины  

В сервисе **Compute Engine** создана виртуальная машина со следующими параметрами:

- **Название:** `vborisova-vm-lab1`  
- **Тип:** e2-micro  
- **Режим:** Spot  

*(Скриншот 2 — создание VM)*  

---

### 3. Подключение к VM  

Подключение выполнено через SSH из веб-консоли GCP.  

*(Скриншот 3 — SSH подключение)*  

---

### 4. Копирование файлов из Cloud Storage  

С помощью команды:

```bash
gcloud storage cp gs://lab1-bucket-itmo/* .

были скопированы файлы из bucket в локальную директорию VM.

Проверка выполнена командой:

```bash
ls -lah

Файлы успешно отображаются в системе.

---

### 5. Изменение роли Service Account  

Роль сервисного аккаунта была изменена:

- **Было:** Storage Admin  
- **Стало:** Compute Viewer  

*(Скриншот 5 — изменение роли)*  

---

### 6. Повторная проверка доступа  

После изменения роли повторно выполнена команда:

```bash
gcloud storage cp gs://lab1-bucket-itmo/* .

Файлы были успешно скопированы, несмотря на отсутствие роли доступа к Cloud Storage.

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
