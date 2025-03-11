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

![image](https://github.com/user-attachments/assets/6148b8f5-1210-4129-b6c3-ed923854c462)

Пишет, что обе утилиты уже установлены. 

Загружаем файл репозиторий, с помощью команды 

`sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo`

![image](https://github.com/user-attachments/assets/c7123886-fbb9-45ff-a3e0-c050af12c5dd)

Устанавливаем Docker, введя команду 

`sudo yum install docker-ce docker-ce-cli containerd.io`

![image](https://github.com/user-attachments/assets/dbfa11bb-8ee1-4709-9172-5b718fcb1ddf)

![image](https://github.com/user-attachments/assets/0ca81b4c-8baa-45ac-adf5-edbd831afc77)

![image](https://github.com/user-attachments/assets/7dbe4edd-21dc-4d12-9ad7-a969c2720604)

После завершения установки Docker, с помощью команды 

`sudo systemctl enable docker --now`

я запустила его и разрешила автозапуск.

![image](https://github.com/user-attachments/assets/e2a803e9-ae2c-4e2d-a09f-e791b97e856b)

На этом работа на паре была завершена!)
