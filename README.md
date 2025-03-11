25.01.2025

В ходе проделанной работы за всю пару, с горем пополам, была создана виртуальная машина.

01.02.2025

В ходе проделанной работы в ранее установленную виртуальную машину были установлены гостевые дополнения.

После чего в командной строке была прописана команда 

`sudo yum install wget`

которая используется для установки утилиты `wget` на системах с пакетным менеджером `yum`.

![image](https://github.com/user-attachments/assets/3a9c6a29-ff6b-414a-852b-444825aacbe6)


При выполнении команды возникла ошибка: 

`malinovskayaai is not in the sudoers file. This incident will be reported.`

Это указывало на то, что текущий пользователь не имеет прав на выполнение команд с использованием `sudo`.

Для исправления ошибки, в командной строке была введена команда 

`su root`

чтобы переключиться на учетную запись суперпользователя (root).

![image](https://github.com/user-attachments/assets/d50c8b2a-52ac-4858-ac4e-ea7312252d00)


После этого был открыт файл 

`nano /etc/sudoers`

чтобы добавить необходимые права для пользователя.

![image](https://github.com/user-attachments/assets/bdbad25c-4624-43f7-a750-135a0c317039)

После введения команды, был открыт терминал где после строки 
`root ALL=(ALL) ALL`

Было введено 

`malinovskayaai ALL=(ALL) ALL`

![image](https://github.com/user-attachments/assets/e551fd7a-94d3-42f6-aaae-4ef93da2200d)


Общий скриншот проделанной работы

![image](https://github.com/user-attachments/assets/19373a02-df7e-47b7-b24b-790cfb44ea02)


По завершению исправления ошибки, я перешла в новую вкладку терминала(командной строки) и снова ввела команду 

`sudo yum install wget`

чтобы проверить, установилась ли утилита wget.

![image](https://github.com/user-attachments/assets/f45debc5-6888-4115-b5e0-ce43a155b599)

На этом работа на паре была закончена.


08.02.2025

Сегодня в процессе выполнения задач, я проверила наличие утилит 

`wget командой: sudo yum install wget`

`curl командой: sudo yum install curl`

![image](https://github.com/user-attachments/assets/f4926c5f-6427-4b98-afde-acd3863aea71)

Видим, что обе утилиты уже установлены. 

Загружаем файл репозиторий, с помощью команды 

`sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo`

![image](https://github.com/user-attachments/assets/56cbe0a8-47f1-4e5d-9670-645dfb953dfe)

Устанавливаем Docker, введя команду 

`sudo yum install docker-ce docker-ce-cli containerd.io`

![image](https://github.com/user-attachments/assets/39d819e6-5e7c-447e-a170-eaa5923bf2fd)

![image](https://github.com/user-attachments/assets/7d52276f-9683-4bf4-a57b-b98ba0d30721)

![image](https://github.com/user-attachments/assets/f392b387-babd-4e91-8ffa-d8e4764ce26e)

После завершения установки Docker, с помощью команды 

`sudo systemctl enable docker --now`

я запустила его и разрешила автозапуск.

![image](https://github.com/user-attachments/assets/70b15bcf-cce9-4cfb-842d-5bb3d18ccbe6)

На этом работа на паре была завершена!)

15.02.2025

![image](https://github.com/user-attachments/assets/9d828263-256c-4d1d-af06-8bc2c6e2dda6)

![image](https://github.com/user-attachments/assets/fb905291-d83d-438b-b0fa-f87235ae5499)

![image](https://github.com/user-attachments/assets/aaadde65-6ecb-42a2-8a16-3d36541d4cbb)

![image](https://github.com/user-attachments/assets/b91f4085-7a31-4c0e-83a0-134564581747)

![image](https://github.com/user-attachments/assets/e1476a28-ff57-4a6d-924d-cda788df2f33)

![image](https://github.com/user-attachments/assets/d1e3d913-fdc5-4af8-85d4-716024363c32)

![image](https://github.com/user-attachments/assets/9fa49fb9-3803-4855-ac8d-26572f67ef6f)

![image](https://github.com/user-attachments/assets/744cc10f-207d-49cc-9fb2-eb1874be316f)

![image](https://github.com/user-attachments/assets/0aabe9e6-e636-40ca-9389-d67cd7bcb320)

![image](https://github.com/user-attachments/assets/b50cc857-5ace-4807-bddf-120caef494a3)

![image](https://github.com/user-attachments/assets/32a38916-0fa6-42cc-875e-83ccbe5620e4)

![image](https://github.com/user-attachments/assets/83eb2228-e617-4f5c-a4e8-68ccfcfbb402)




