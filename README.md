# DA-in-GameDev-lab2
Отчёт по лабораторной работе #2 выполнил:
- Усик Артемий Максимович
-  РИ230915

| Задание|Выполнение|Баллы|
| ------ | --------| ---- |
|Задание 1| * | 10 |
|Задание 2| * | 15 |
|Задание 3| * | 5  |
|Задание 4| * | 35 |
|Задание 5| # | 35 |


## Цель работы 
Научиться передавать в Unity данные из Google Sheets с помощью Python.

## Задание 1
### Настроить доступ к google-таблице по api.
Ход работы:
- Перешли по ссылке https://console.cloud.google.com
- Создали новый проект, выбрав Select a project - New project
- Дайли имя проекту и нажмите кнопку Create
![2024-10-29_12-10-35](https://github.com/user-attachments/assets/1aaa3b6d-8098-41e1-a71f-38fefa828f3c)
- Перешли в Dashboard созданного проекта
![2024-10-29_12-12-49](https://github.com/user-attachments/assets/1084d743-b95f-48fc-9168-8809099067dc)
- Перешли в google drive api, используя строку поиска
![2024-10-29_12-13-55](https://github.com/user-attachments/assets/9fa9c31d-306a-4630-84dc-c66ed51acd9a)
- Нажали кнопку Enable API:
![2024-10-29_12-15-59](https://github.com/user-attachments/assets/94a22d7d-76c0-411f-83e1-f84572d20f67)
===
![2024-10-29_12-18-27](https://github.com/user-attachments/assets/098ddee4-8fe3-459e-94fe-7cf63963d21c)
===
![2024-10-29_12-19-08](https://github.com/user-attachments/assets/8b3089e7-e2f8-4125-854e-b96f362fe1ac)
===
![2024-10-29_12-19-58](https://github.com/user-attachments/assets/83e521f0-4a49-49b5-8bc0-c7a32ddd0d98)
===
![2024-10-29_12-20-39](https://github.com/user-attachments/assets/b42eac3f-a620-45b7-9f96-ff855b17fefb)
===
![2024-10-29_12-23-01](https://github.com/user-attachments/assets/c96fec6e-6a10-4525-b12b-2df692c39248)

- Завершили создание, нажав кнопку Done
- Сохранили файл с ключом в формате json на свой компьютер
- Скопировали адрес сервисного аккаунта
- Создали google-таблицу и открыли к ней доступ для редактирования с созданного сервисного аккаунта
![2024-10-29_12-26-13](https://github.com/user-attachments/assets/548ca29d-980a-4047-b143-88595b8fade5)

  
## Задание 2
###  Генерация данных с помощью Python и их передача в google таблицу.
Ход работы:
- Запустили Jupyter Notebook, создали новый .ipynb-файл. Сделали так, чтобы созданный файл и скачанный ранее .json-файл с ключами оказался в одной директории
![2024-10-29_12-28-02](https://github.com/user-attachments/assets/169966a4-ee08-42e1-b3d2-83d841b3d406)
===
- В .ipynb файле на языке Python реализовали передачу данных в созданную ранее google-таблицу. Реализация на Python рассчитывает темп инфляции для экономической модели:

```py

import gspread
import numpy as np
gc = gspread.service_account(filename='night-internships-257f9ea336c0.json')
sh = gc.open("NightsInterships")
price = np.random.randint(2000, 10000, 11)
mon = list(range(1,11))
i = 0
while i <= len(mon):
    i += 1
    if i == 0:
        continue
    else:
        tempInf = ((price[i-1]-price[i-2])/price[i-2])*100
        tempInf = str(tempInf)
        tempInf = tempInf.replace('.',',')
        sh.sheet1.update(('A' + str(i)), str(i))
        sh.sheet1.update(('B' + str(i)), str(price[i-1]))
        sh.sheet1.update(('C' + str(i)), str(tempInf))
        print(tempInf)

```
- Для корректной работы потребуется gspread. Мы установили этот пакет из Anaconda Powershell Prompt


## Задание 3
###  Создание ключа API для передачи данных из google-таблицы в Unity.
Ход работы:

## Задание 4
###  Новый проект на Unity.
Ход работы:

## Выводы


## Powered by

**Усик Артемий Максимович|Yakut**
