# Malinovskaya Arina K-ISP-39-1

Создана виртуальная машина - Linux;

Оперативная память - 2048ж

Процессор(ы) - 2;

Размер диска 20,00 Гб.

При установке необходимо создать учетную запись (задать логин и пароль), а также выбрать английский язык для виртуальной машины.

В ранее установленную виртуальную машину были установлены гостевые дополнения.

![image](https://github.com/user-attachments/assets/538b4cf4-0ecd-425b-bef5-c1307b25ed8c)

![image](https://github.com/user-attachments/assets/a5fdbd81-8eff-4949-8a07-53e2bdb31dc5)

Приступаем к работе с командной строкой:

1. `sudo yum install wget`

• используется для установки утилиты `wget` на системах с пакетным менеджером `yum`.

![image](https://github.com/user-attachments/assets/3a9c6a29-ff6b-414a-852b-444825aacbe6)

! При выполнении команды возникла ошибка: !

`malinovskayaai is not in the sudoers file. This incident will be reported.`

Это указывало на то, что текущий пользователь не имеет прав на выполнение команд с использованием `sudo`.

Для исправления ошибки, в командной строке была введена команда 

`su root`

• чтобы переключиться на учетную запись суперпользователя (root).

![image](https://github.com/user-attachments/assets/d50c8b2a-52ac-4858-ac4e-ea7312252d00)

После этого был открыт файл 

`nano /etc/sudoers`

• чтобы добавить необходимые права для пользователя.

![image](https://github.com/user-attachments/assets/bdbad25c-4624-43f7-a750-135a0c317039)

После введения команды, был открыт терминал 

• insert - исправит/внести изменения.

После строки `root ALL=(ALL) ALL`, было введено: 

`malinovskayaai ALL=(ALL) ALL`

• Esc --> q! - Не сохранять изменения;

• Ecs --> wq! - Сохранить изменения. 

![image](https://github.com/user-attachments/assets/e551fd7a-94d3-42f6-aaae-4ef93da2200d)

2. Проверка наличия утилит `wget` и `curl`

`sudo yum install wget`

`sudo yum install curl`

![image](https://github.com/user-attachments/assets/f4926c5f-6427-4b98-afde-acd3863aea71)

• Видим, что обе утилиты уже установлены. 

3. Загружаем файл репозиторий

`sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo`

![image](https://github.com/user-attachments/assets/56cbe0a8-47f1-4e5d-9670-645dfb953dfe)

4. Устанавливаем Docker

`sudo yum install docker-ce docker-ce-cli containerd.io`

![image](https://github.com/user-attachments/assets/39d819e6-5e7c-447e-a170-eaa5923bf2fd)

![image](https://github.com/user-attachments/assets/7d52276f-9683-4bf4-a57b-b98ba0d30721)

![image](https://github.com/user-attachments/assets/f392b387-babd-4e91-8ffa-d8e4764ce26e)

5. Запускаем его и разрешаем автозапуск

`sudo systemctl enable docker --now`

![image](https://github.com/user-attachments/assets/70b15bcf-cce9-4cfb-842d-5bb3d18ccbe6)

15.02.2025

![image](https://github.com/user-attachments/assets/9d828263-256c-4d1d-af06-8bc2c6e2dda6)

![image](https://github.com/user-attachments/assets/fb905291-d83d-438b-b0fa-f87235ae5499)

![image](https://github.com/user-attachments/assets/aaadde65-6ecb-42a2-8a16-3d36541d4cbb)

![image](https://github.com/user-attachments/assets/b91f4085-7a31-4c0e-83a0-134564581747)

![image](https://github.com/user-attachments/assets/e1476a28-ff57-4a6d-924d-cda788df2f33)

![image](https://github.com/user-attachments/assets/d1e3d913-fdc5-4af8-85d4-716024363c32)

![image](https://github.com/user-attachments/assets/9fa49fb9-3803-4855-ac8d-26572f67ef6f)

![image](https://github.com/user-attachments/assets/212b0265-5d78-4d7b-a82c-9c69950dd438)

![image](https://github.com/user-attachments/assets/0aabe9e6-e636-40ca-9389-d67cd7bcb320)

![image](https://github.com/user-attachments/assets/b50cc857-5ace-4807-bddf-120caef494a3)

![image](https://github.com/user-attachments/assets/32a38916-0fa6-42cc-875e-83ccbe5620e4)

![image](https://github.com/user-attachments/assets/83eb2228-e617-4f5c-a4e8-68ccfcfbb402)

![image](https://github.com/user-attachments/assets/56121bef-f7c8-4e1d-ac6d-21eb2db814cd)

![image](https://github.com/user-attachments/assets/c9a4404d-21ce-496b-af8d-3a0c19a6216f)

![image](https://github.com/user-attachments/assets/313c5462-0a6d-4379-830e-dc61d3c2836e)

![image](https://github.com/user-attachments/assets/f993384a-2e34-411f-8830-4129bca68e86)

..
![image](https://github.com/user-attachments/assets/3c85685e-f84e-4974-99df-8710f89bf282)
..

другая пара
1.
![image](https://github.com/user-attachments/assets/c01128ce-fdda-467f-99e4-425790efe2b0)

![image](https://github.com/user-attachments/assets/73c3692b-149a-44b4-a904-39128b1de947)
 
2. 
![image](https://github.com/user-attachments/assets/855d8322-c236-453b-9dcf-531b7b48d6ca)

![image](https://github.com/user-attachments/assets/0053ba1f-6a15-4c4a-a8ee-a0591d655c54)

3. 






