# **Лабораторна робота №2**

-----------------------------------
## Необхідні ресурси:
- Встановлений компілятор для Python.

## Інформація про програму:
- Виводить в терміналі "Hello World!".
- Виконує команди: ping, echo, login, list, msg, file, exit.

## Опис Команд:
### 1. Команда `ping <Address: String>`.
#### Ця команда перевіряє зєднання з сервером, сайтом чи будь-яким іншим пристроєм за вказаною IP або DNS адресою. Дані команді передається тільки один параметр - `<Address: String>`
#### Результатом виконання у разі успішного зєднання в першому рядку записується `Ping <Address: String> ...` і в наступному рядку `Ping <Address: String> request success.`.
#### Якщо ж кількість введених параметрів не буде рівна "1", то замість результату виводиться повідомлення з описом помилки в дужках`PING ERROR (Incorect input argument)`

### Приклад виконання команди:
```text
>>> 
===== RESTART: C:\Users\roma2\Documents\GitHub\Distributed-IKS\Lab2\Lab2.py ====
Hello World!
========================================
Input Command: ping youtube.com
Entered command = "ping", parameters = ['youtube.com']
----------------------------------------

Results:
Ping youtube.com ...
Ping youtube.com request success.
========================================
Input Command: ping 192.168.1.0
Entered command = "ping", parameters = ['192.168.1.0']
----------------------------------------

Results:
Ping 192.168.1.0 ...
Ping 192.168.1.0 request success.
========================================
Input Command: ping
Entered command = "ping", parameters = []
----------------------------------------

Results:
PING ERROR (Incorect input argument)
========================================
Input Command: ping yahoo.com telegram.com
Entered command = "ping", parameters = ['yahoo.com', 'telegram.com']
----------------------------------------

Results:
PING ERROR (Incorect input argument)
```

### 2. Команда `echo <anyText: String> <anyText: String> ...`.
#### Ця команда виводить на екрані текст з вхідних параметрів - `<anyText: String>`. Ця команда може отримувати будь-яку кількість параметрів. Кожний параметр відображається в новому рядку.

### Приклад виконання команди:
```text
>>> 
===== RESTART: C:\Users\roma2\Documents\GitHub\Distributed-IKS\Lab2\Lab2.py ====
Hello World!
========================================
Input Command: echo hello
Entered command = "echo", parameters = ['hello']
----------------------------------------

Results:
hello
========================================
Input Command: echo Pavliuk Lab 2
Entered command = "echo", parameters = ['Pavliuk', 'Lab', '2']
----------------------------------------

Results:
Pavliuk
Lab
2
========================================
Input Command: Lab Ended
Entered command = "Lab", parameters = ['Ended']
----------------------------------------

Results:
No Command = "Lab"
```

### 3. Команда `login <login: String> <password: String>`.
#### Ця команда дозволяє користувачу залогінитися. Дані команді передається два параметри - `<login: String>` і `<password: String>`.
#### Результатом виконання команди буде:
- Якщо логін даного користувача немає в базі даних, то в консолі виводиться `LOGIN ERROR (Incorect input login or password)`.
- Якщо логін даного користувача є в базі даних, але відповідний до нього пароль введений неправильно, то в консолі виводиться `LOGIN ERROR (Incorect input login or password)`.
- Якщо логін даного користувача є в базі даних, і відповідний до нього пароль введений правильно, то в першому рядку консолі виводиться - `LOGIN SUCCESS:`, а в наступному рядку - `Hello, <nameUsers: String>`.
- Якщо кількість введених параметрів не дорівнює 2, то в консолі виводиться `LOGIN ERROR (Incorect input argument)`.

### Приклад виконання команди:
```text
=========================== RESTART: C:\Users\roma2\Documents\GitHub\Distributed-IKS\Lab2\Lab2.py ==========================
Hello World!
========================================
Input Command: list
Entered command = "list", parameters = []
----------------------------------------

Results:
1. Bogdan
2. Ivan
3. Arsen
4. Kate
========================================
Input Command: login Bogdan_std student01
Entered command = "login", parameters = ['Bogdan_std', 'student01']
----------------------------------------

Results:
LOGIN SUCCESS:
 Hello, Bogdan
========================================
Input Command: login Bogdan_std 1111
Entered command = "login", parameters = ['Bogdan_std', '1111']
----------------------------------------

Results:
LOGIN ERROR (Incorect input login or password)
========================================
Input Command: login Ivan_std Ivan0001
Entered command = "login", parameters = ['Ivan_std', 'Ivan0001']
----------------------------------------

Results:
LOGIN ERROR (Incorect input login or password)
========================================
Input Command: login Arsen student03
Entered command = "login", parameters = ['Arsen', 'student03']
----------------------------------------

Results:
LOGIN ERROR (Incorect input login or password)
```

### 4. Команда `list`.
#### Ця команда виводить на екран список назв всіх зареєстрованих користувачів які знаходяться в базі даних. Для цієї команди не потрібно вводити параметри, якщо було введено параметри то вони ігноруються. Назва кожного користувача відображається в новому рядку з його поряковим номером - `<№Users: Int>. <nameUsers: String>` .
#### База даних:
- user_names = `Bogdan`, `Ivan`, `Arsen`, `Kate`
- user_logins = `Bogdan_std`, `Ivan_std`, `Arsen_std`, `Kate_std`
- user_passwords = `student01`, `student02`, `student03`, `student04`

### Приклад виконання команди:
```text
=========================== RESTART: C:\Users\roma2\Documents\GitHub\Distributed-IKS\Lab2\Lab2.py ==========================
Hello World!
========================================
Input Command: list
Entered command = "list", parameters = []
----------------------------------------

Results:
1. Bogdan
2. Ivan
3. Arsen
4. Kate
========================================
Input Command: list lab
Entered command = "list", parameters = ['lab']
----------------------------------------

Results:
1. Bogdan
2. Ivan
3. Arsen
4. Kate
```

### 5. Команда `msg <destinationUser: String> <text: String>`.
#### Ця команда надсилає текстове повідомлення іншому користувачу. Дані команді передається два параметри - `<destinationUser: String>` і ` <text: String>`.
#### Результатом виконання команди буде:
- Якщо назви даного користувача немає в базі даних, то в консолі виводиться `MESSAGE SENDING ERROR (This user not found)`.
- Якщо назва даного користувача є в базі даних, то в консолі виводиться `MESSAGE SENDING SUCCESS`.
- Якщо кількість введених параметрів не дорівнює 2, то в консолі виводиться `MESSAGE SENDING ERROR (Incorect input argument)`.

### Приклад виконання команди:
```text
>>> 
=========================== RESTART: C:\Users\roma2\Documents\GitHub\Distributed-IKS\Lab2\Lab2.py ==========================
Hello World!
========================================
Input Command: msg Ivan "Lab Ended"
Entered command = "msg", parameters = ['Ivan', 'Lab Ended']
----------------------------------------

Results:
MESSAGE SENDING SUCCESS
========================================
Input Command: Andriy "lab2"
Entered command = "Andriy", parameters = ['lab2']
----------------------------------------

Results:
No Command = "Andriy"
========================================
Input Command: msg Andriy "lab2"
Entered command = "msg", parameters = ['Andriy', 'lab2']
----------------------------------------

Results:
MESSAGE SENDING ERROR (This user not found)
========================================
Input Command: msg Kate
Entered command = "msg", parameters = ['Kate']
----------------------------------------

Results:
MESSAGE SENDING ERROR (Incorect input argument)
```

### 6. Команда `file <destinationUser: String> <filename: String>`.
#### Ця команда надсилає файлове повідомлення іншому користувачу. Дані команді передається два параметри - `<destinationUser: String>` і ` <filename: String>`.
#### Результатом виконання команди буде:
- Якщо назви даного користувача немає в базі даних, то в консолі виводиться `FILE SENDING ERROR (User not found)`.
- Якщо назва даного користувача є в базі даних, але даного файлу немає, то в консолі виводиться `FILE SENDING ERROR (File not found)`.
- Якщо назва даного користувача є в базі даних, і цей файл існує, то в консолі виводиться `FILE SENDING SUCCESS`.
- Якщо кількість введених параметрів не дорівнює 2, то в консолі виводиться `FILE SENDING ERROR (Incorect input argument)`.

### Приклад виконання команди:
```text
=========================== RESTART: C:\Users\roma2\Documents\GitHub\Distributed-IKS\Lab2\Lab2.py ==========================
Hello World!
========================================
Input Command: file Kate README.md
Entered command = "file", parameters = ['Kate', 'README.md']
----------------------------------------

Results:
FILE SENDING SUCCESS
========================================
Input Command: file Ivan lab
Entered command = "file", parameters = ['Ivan', 'lab']
----------------------------------------

Results:
FILE SENDING ERROR (File not found)
========================================
Input Command: file Arsen Lab2.py
Entered command = "file", parameters = ['Arsen', 'Lab2.py']
----------------------------------------

Results:
FILE SENDING SUCCESS
========================================
Input Command: file 01
Entered command = "file", parameters = ['01']
----------------------------------------

Results:
FILE SENDING ERROR (Incorect input argument)

```

### 7. Команда `exit`.
#### Ця команда виходить з циклу для опитування введення команд. Для цієї команди не потрібно вводити параметри, якщо було введено параметри то вони ігноруються.
- Результатом виконання команди буде - `Exit from cycle`

### Приклад виконання команди:
```text
>>> 
=========================== RESTART: C:\Users\roma2\Documents\GitHub\Distributed-IKS\Lab2\Lab2.py ==========================
Hello World!
========================================
Input Command: list
Entered command = "list", parameters = []
----------------------------------------

Results:
1. Bogdan
2. Ivan
3. Arsen
4. Kate
========================================
Input Command: exit 1
Entered command = "exit", parameters = ['1']
----------------------------------------

>>> 
=========================== RESTART: C:\Users\roma2\Documents\GitHub\Distributed-IKS\Lab2\Lab2.py ==========================
Hello World!
========================================
Input Command: list
Entered command = "list", parameters = []
----------------------------------------

Results:
1. Bogdan
2. Ivan
3. Arsen
4. Kate
========================================
Input Command: exit
Entered command = "exit", parameters = []
----------------------------------------

Results:
Exit from cycle
```

### Примітка: щоб ввести текст в якому містяться символ " " потрібно використовувати адинарні або подвійні дужки в кінці і на початку тексту.
### Примітка: Якщо було некоректно введено команду або її не існує, то в консолі виводиться `No Command = "<comand>"`.

### Приклад спроби виконання іншої команди:
```text
>>> 
=========================== RESTART: C:\Users\roma2\Documents\GitHub\Distributed-IKS\Lab2\Lab2.py ==========================
Hello World!
========================================
Input Command: command 1
Entered command = "command", parameters = ['1']
----------------------------------------

Results:
No Command = "command"
========================================
Input Command:  test echo lab2
Entered command = "", parameters = ['test', 'echo', 'lab2']
----------------------------------------

Results:
No Command = ""
```
