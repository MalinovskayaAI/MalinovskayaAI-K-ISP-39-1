# Malinovskaya Arina K-ISP-39-1

![image](https://github.com/user-attachments/assets/88f68074-6aa9-4c4a-993f-e45e6a93ba71)

Создана виртуальная машина - Linux;

Оперативная память - 8000;

Процессор(ы) - 2;

Размер диска 20,00 Гб.

При установке необходимо создать учетную запись (задать логин и пароль), а также выбрать английский язык для виртуальной машины.

В ранее установленную виртуальную машину были установлены гостевые дополнения.

![image](https://github.com/user-attachments/assets/538b4cf4-0ecd-425b-bef5-c1307b25ed8c)

![image](https://github.com/user-attachments/assets/a5fdbd81-8eff-4949-8a07-53e2bdb31dc5)

Приступаем к работе с командной строкой:

1. Устанавливаем утилиты `wget` на системы с пакетным менеджером `yum`

```bash
sudo yum install wget
```

![image](https://github.com/user-attachments/assets/3a9c6a29-ff6b-414a-852b-444825aacbe6)

! При выполнении команды возникла ошибка: !

`malinovskayaai is not in the sudoers file. This incident will be reported.`

Это указывало на то, что текущий пользователь не имеет прав на выполнение команд с использованием `sudo`.

Для исправления ошибки, в командной строке была введена команда 

```bash
su root
```

• чтобы переключиться на учетную запись суперпользователя (root).

![image](https://github.com/user-attachments/assets/d50c8b2a-52ac-4858-ac4e-ea7312252d00)

После этого был открыт файл 

```bash
nano /etc/sudoers
```

• чтобы добавить необходимые права для пользователя.

![image](https://github.com/user-attachments/assets/bdbad25c-4624-43f7-a750-135a0c317039)

После введения команды, был открыт терминал 

• insert - внести изменения.

После строки `root ALL=(ALL) ALL`, было введено: 

```bash
malinovskayaai ALL=(ALL) ALL
```

• Esc --> q! - Не сохранять изменения;

• Ecs --> wq! - Сохранить изменения. 

![image](https://github.com/user-attachments/assets/e551fd7a-94d3-42f6-aaae-4ef93da2200d)

2. Проверка наличия утилит `wget` и `curl`

```bash
sudo yum install wget
```

```bash
sudo yum install curl
```

![image](https://github.com/user-attachments/assets/f4926c5f-6427-4b98-afde-acd3863aea71)

• Видим, что обе утилиты уже установлены. 

3. Загружаем файл репозиторий

```bash
sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo
```

![image](https://github.com/user-attachments/assets/56cbe0a8-47f1-4e5d-9670-645dfb953dfe)

4. Устанавливаем Docker

```bash
sudo yum install docker-ce docker-ce-cli containerd.io
```

![image](https://github.com/user-attachments/assets/39d819e6-5e7c-447e-a170-eaa5923bf2fd)

![image](https://github.com/user-attachments/assets/7d52276f-9683-4bf4-a57b-b98ba0d30721)

![image](https://github.com/user-attachments/assets/f392b387-babd-4e91-8ffa-d8e4764ce26e)

5. Запускаем его и разрешаем автозапуск

```bash
sudo systemctl enable docker --now
```

![image](https://github.com/user-attachments/assets/70b15bcf-cce9-4cfb-842d-5bb3d18ccbe6)

6. • Объявление переменной `COMVER`, полученной в результате `curl` запроса, хранящей в себе номер последней
версии Docker Compose

```bash
COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)
```

![image](https://github.com/user-attachments/assets/9d828263-256c-4d1d-af06-8bc2c6e2dda6)

7. Cкачиваем скрипт `docker-compose` последней версии, используя объявленную ранее переменную и помещаем его в каталог `/usr/bin`

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose
```

![image](https://github.com/user-attachments/assets/fb905291-d83d-438b-b0fa-f87235ae5499)

8. Предоставление прав на выполнение файла `docker-compose`

```bash
sudo chmod +x /usr/bin/docker-compose
```

![image](https://github.com/user-attachments/assets/aaadde65-6ecb-42a2-8a16-3d36541d4cbb)

9. Проверка установленной версии Docker Compose

```bash
docker-compose --version
```

![image](https://github.com/user-attachments/assets/b91f4085-7a31-4c0e-83a0-134564581747)

10. Установка `git` с помощью командной строки

```bash
git clone https://github.com/skl256/grafana_stack_for_docker.git
```

! Выдает ошибку !

![image](https://github.com/user-attachments/assets/e1476a28-ff57-4a6d-924d-cda788df2f33)

Устранкение ошибки.

```bash
sudo yum install git-core
```

![image](https://github.com/user-attachments/assets/d1e3d913-fdc5-4af8-85d4-716024363c32)

Установка `git`

```bash
git clone https://github.com/skl256/grafana_stack_for_docker.git
```

![image](https://github.com/user-attachments/assets/9fa49fb9-3803-4855-ac8d-26572f67ef6f)

11. Переход в директорию

```bash
cd grafana_stack_for_docker
```

![image](https://github.com/user-attachments/assets/212b0265-5d78-4d7b-a82c-9c69950dd438)

12. Создаем полный путь `/mnt/common_volume/swarm/grafana/config`, включая все необходимые промежуточные каталоги, если они ещё не существуют

```bash
sudo mkdir -p /mnt/common_volume/swarm/grafana/config
```

![image](https://github.com/user-attachments/assets/0aabe9e6-e636-40ca-9389-d67cd7bcb320)

13. Создаём структуру каталогов для Grafana и связанных с ней компонентов, если они ещё не существуют

```bash
sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}
```

![image](https://github.com/user-attachments/assets/b50cc857-5ace-4807-bddf-120caef494a3)

14. Все файлы и каталоги в указанных директориях передаем в собственность текущему пользователю и его группе

```bash
sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}
```

![image](https://github.com/user-attachments/assets/32a38916-0fa6-42cc-875e-83ccbe5620e4)

15. Файл `grafana.ini` уже существует, команда обновит его временные метки.
    Если файл не существует, команда создаст новый пустой файл с указанным именем по указанному пути.

```bash
touch /mnt/common_volume/grafana/grafana-config/grafana.ini
```

![image](https://github.com/user-attachments/assets/2e10c426-519d-45f5-b953-98b10a386c0e)

![image](https://github.com/user-attachments/assets/83eb2228-e617-4f5c-a4e8-68ccfcfbb402)

16. Команда копирует все файлы и подкаталоги из директории `config` в директорию `/mnt/common_volume/swarm/grafana/config/`

```bash
cp config/* /mnt/common_volume/swarm/grafana/config/
```

![image](https://github.com/user-attachments/assets/a137703f-179c-4a9d-9d92-70ccb989f9af)

![image](https://github.com/user-attachments/assets/56121bef-f7c8-4e1d-ac6d-21eb2db814cd)

17. Команда переименовывает файл `grafana.yaml` в `docker-compose.yaml.` Ничего не покажет, но можно проверить при помощи команды `ls`

```bash
mv grafana.yaml docker-compose.yaml
```

![image](https://github.com/user-attachments/assets/c9a4404d-21ce-496b-af8d-3a0c19a6216f)

18. Команда создает и запускает контейнеры в фоновом режиме, используя конфигурацию из файла `docker-compose.yml`, с правами суперпользователя.

```bash
sudo docker compose up -d
```

![image](https://github.com/user-attachments/assets/9c9e5482-3a50-46af-9175-f28c6b0b4622)

![image](https://github.com/user-attachments/assets/38b0a263-ef2b-4178-9804-b908891231a4)

19. Команда открывает файл `docker-compose.yaml` в текстовом редакторе `vi` с правами суперпользователя, что позволяет вам редактировать его содержимое

```bash
sudo vi docker-compose.yaml
```

• Нас перекинет в текстовый редактор

• Нажимаем на клавиатуре insert - чтобы внести изменения.

После `services` нужно поставить `node-exporter`

• Esc --> q! - Не сохранять изменения;

• Ecs --> wq! - Сохранить изменения. 

![image](https://github.com/user-attachments/assets/c01128ce-fdda-467f-99e4-425790efe2b0)

![image](https://github.com/user-attachments/assets/73c3692b-149a-44b4-a904-39128b1de947)
 
20. С помощью команды открываем файл `prometheus.yaml` в текстовом редакторе `vi` с правами суперпользователя

• Нас перекинет в текстовый редактор

• Нажимаем на клавиатуре insert - чтобы внести изменения.

 В строке `targets:` были исправлкены первые значения на `exporter:9100`

• Esc --> q! - Не сохранять изменения;

• Ecs --> wq! - Сохранить изменения. 

![image](https://github.com/user-attachments/assets/855d8322-c236-453b-9dcf-531b7b48d6ca)

![image](https://github.com/user-attachments/assets/0053ba1f-6a15-4c4a-a8ee-a0591d655c54)

21. Можем создать и запустить контейнеры в фоновом режиме, если они не запущены

```bash
sudo docker compose up -d
```

![image](https://github.com/user-attachments/assets/e67eadb7-52a6-4fcb-812d-e6b590b2f8ca)

22. Можем остановить запущенные контейнеры без их удаления

```bash
sudo docker compose stop
```

![image](https://github.com/user-attachments/assets/9f07e2b5-5b05-4e74-83aa-e1dc602776f0)

23. Остановка и удаление контейнеров, сетей, томов и других ресурсов, созданных с помощью Docker Compose

```bash
sudo docker compose down
```

![image](https://github.com/user-attachments/assets/94eaca40-aa3e-44fe-9350-cd51fe554adc)

## Работа с репозиторием и его файлами

1. Клонирование репозитория MalinovskayaAI-K-ISP-39-1 с GitHub

```bash
sudo git clone https://github.com/MalinovskayaAI/MalinovskayaAI-K-ISP-39-1.git
```

![image](https://github.com/user-attachments/assets/75ae2097-d1a4-4215-a60c-5b5d64e8d6b2)

2. Переход в каталог MalinovskayaAI-K-ISP-39-1 и просмотр файлов

```bash
cd MalinovskayaAI-K-ISP-39-1
ls
```

![image](https://github.com/user-attachments/assets/f4138a08-31d4-4360-b0b7-98d17374db98)

4. Открытие файла README.md с правами sudo.

```bash
sudo rm README.md
ls
```

![image](https://github.com/user-attachments/assets/d17f25d3-bc35-4a1d-9a2a-684e306e48fd)

5. Просмотр/вывод полного пути текущего каталога

```bash
pwd
```

![image](https://github.com/user-attachments/assets/55908c3e-be55-4db1-a174-65088edc99aa)

6. Просмотр проделанной работы

![image](https://github.com/user-attachments/assets/fb923dd6-90b8-4cec-93e7-f26c7e663400)

![image](https://github.com/user-attachments/assets/16c7dacc-c47b-4c8f-a4e1-6d84a6cccfbe)


## Grafana

Сайт/вход

Переходим на работу с `Grafana` переходим на сайт `localhost:3000`.

Пользователь и пароль: `admin`.

Код графаны `1816`.

Код прометеуса: `http://prometheus:9090`.

![image](https://github.com/user-attachments/assets/fc85c707-78bc-49a8-a067-b0902bf95c47)

Создание новой `New Dashboard` 

![image](https://github.com/user-attachments/assets/d10c283e-060e-419f-8eee-286d800473e7)

Выбор прометеуса

![image](https://github.com/user-attachments/assets/76bf2b6e-82c4-4cca-8edf-50344a8b0e37)

конекшн url

![image](https://github.com/user-attachments/assets/6e6804c3-81b1-4421-a9af-8d1d8128b07c)

аунтификация

![image](https://github.com/user-attachments/assets/85293a69-7bcb-4791-97ae-1273216cefc1)

зеленая галочка

![image](https://github.com/user-attachments/assets/4f104711-dc60-4027-863b-ad2ec4c65191)

общий скрин

![image](https://github.com/user-attachments/assets/032f633d-fa64-4212-b7df-4ff657963f18)

диаграммы

![image](https://github.com/user-attachments/assets/e98d518a-9cf6-4527-b032-a496c059f465)


## ViktoriaMetrics

Далее пойдет работа с Victoria Metrics переходим на сайт

```bash
http://localhost:8428/
```

![image](https://github.com/user-attachments/assets/aebe7c65-ecf7-4bab-9266-22e83399e082)

Такеже в соседней вкладке открываем сайт

```bash
http://localhost:9090/
```

![image](https://github.com/user-attachments/assets/78a209fe-c678-4cd4-b6e5-dae3ee367587)

Заходим на сайт `Grafana` и создаем Victoria Metrics также как и Prometheus только меняем Name на `Viktoria`, URl на `http://victoriametrics:8428` и ставим `No autentification`.

```bash
http://victoriametrics:8428/
```

Сохраняем.

![image](https://github.com/user-attachments/assets/cf1b4d8f-7562-486a-ad8b-b41c44b35ffb)

Проверяем работу и выбираем имя которое мы указали `Viktoria`

![image](https://github.com/user-attachments/assets/047de7eb-2e01-4559-8134-726447244320)

Dыбираем и смоотрим результат

![image](https://github.com/user-attachments/assets/4f81e05a-0e30-44c4-84cf-f114913764ce)

Далее открываем терминал, переходим в папку `grafana_stack_for_docker` и вводим команду

```bash
echo -e "# TYPE light_metric1 gauge\nlight_metric1 0" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus
```

Потом переходим в браузер на первую вкладку Victoria Metrics и выбираем `vmui - Web UI`

![image](https://github.com/user-attachments/assets/715b7728-417a-43a1-8671-4f18719db900)

Вводим в строку 

```bash
light_metric1
```

Видим результат

![image](https://github.com/user-attachments/assets/473b3f6f-48d3-43c2-b2d6-ce33d1b87382)

Переходим обратно в `grafana` и вставляем в строку `light_metric1` и нажимаем `Run queries`

![image](https://github.com/user-attachments/assets/d6fd83ac-bd2d-437e-9c0e-445af553797a)

![image](https://github.com/user-attachments/assets/a5c9562e-2985-429f-a04d-13eca49c20bc)





