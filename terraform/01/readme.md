# Домашнее задание к занятию «Введение в Terraform»

### Задание 1

1. Перейдите в каталог [**src**](https://github.com/netology-code/ter-homeworks/tree/main/01/src). Скачайте все необходимые зависимости, использованные в проекте. 
2. Изучите файл **.gitignore**. В каком terraform-файле, согласно этому .gitignore, допустимо сохранить личную, секретную информацию?
3. Выполните код проекта. Найдите  в state-файле секретное содержимое созданного ресурса **random_password**, пришлите в качестве ответа конкретный ключ и его значение.
4. Раскомментируйте блок кода, примерно расположенный на строчках 29–42 файла **main.tf**.
Выполните команду ```terraform validate```. Объясните, в чём заключаются намеренно допущенные ошибки. Исправьте их.
5. Выполните код. В качестве ответа приложите вывод команды ```docker ps```.
6. Замените имя docker-контейнера в блоке кода на ```hello_world```. Не перепутайте имя контейнера и имя образа. Мы всё ещё продолжаем использовать name = "nginx:latest". Выполните команду ```terraform apply -auto-approve```.
Объясните своими словами, в чём может быть опасность применения ключа  ```-auto-approve```. В качестве ответа дополнительно приложите вывод команды ```docker ps```.
7. Уничтожьте созданные ресурсы с помощью **terraform**. Убедитесь, что все ресурсы удалены. Приложите содержимое файла **terraform.tfstate**. 
8. Объясните, почему при этом не был удалён docker-образ **nginx:latest**. Ответ подкрепите выдержкой из документации [**провайдера docker**](https://docs.comcloud.xyz/providers/kreuzwerker/docker/latest/docs).  

### Ответ 1

1. готово
2. в файле personal.auto.tfvars. В всязи с тем что файл имеет расширение .tfvars .tfvars- это файлы, которые содержат значения переменных, использующихся в файлах конфигурации, включая пароли и ключи.
3. Был создан terraform.tfstate в котором и был создан **random_password**. Храниться он секции "resources" содержащую информацию о всех ресурсах, управляемых Terraform инфраструктурного проекта. Сам пароль находится в графе result": "7O5yPXWbDrdBZDhZ".
4.  Error: Missing name for resource - ошибка в том что нет имени для рессурса, все ресурные блоки должны иметь два наименования (тип и имя). Нужно добавить наименование имени, в моем случае "my_dockimage"
Error: Invalid resource name - ошибка в имени ресурса. Имя ресурса должно начинаться с буквы или подчеркивания, но в нашем случае начинается с цифры "1nginx". Исправляем на "nginx"
Error: Reference to undeclared resource - Ссылка на необъявленный ресурс. ошибка была в name  = "example_${random_password.random_string_FAKE.resulT}" где в result есть заглавная буква. Так же _FAKE неверной синтаксической конструкции
image = docker_image.nginx.image_id - нужно поменять nginx на my_dockimage, чтобы соответствовать объявленному именованию ресурса.
5. ![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/terraform/01/img/Docker%20ps.jpg)
6. -auto-approve это автоматически утвердить план изменений без запроса подтверждения пользователя
Эта команда опасна тем что нежелательные изменения могут быть незамеченны
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/terraform/01/img/4.1%20hello-world.png)
7. ![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/terraform/01/img/destroy.png)
8. ![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/terraform/01/img/final.jpg)

### Задание 2*

1. Изучите в документации provider [**Virtualbox**](https://docs.comcloud.xyz/providers/shekeriev/virtualbox/latest/docs) от 
shekeriev.
2. Создайте с его помощью любую виртуальную машину. Чтобы не использовать VPN, советуем выбрать любой образ с расположением в GitHub из [**списка**](https://www.vagrantbox.es/).

В качестве ответа приложите plan для создаваемого ресурса и скриншот созданного в VB ресурса. 

------

