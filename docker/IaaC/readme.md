# IaaC homework
## Задача 1
1) Опишите основные преимущества применения на практике IaaC-паттернов.
2) Какой из принципов IaaC является основополагающим?
### Ответ 2
1) Основные приемущества применения на практике заключаются в автоматизировании работы через конфигурационные файлы, а не через ручное редактирование конфигурации на серверах  или интерактивное взаимодействие. Например вместо того что бы создавать десятки однотипных серверов и установки ПО на них вручную, можно этот процесс автоматизировать с помощью IaaC (инфраструктура как код)
2) Основополагающим принципом IaaC является :
1.Ускорение производства и вывода продукта на рынок
2.Стабильность среды, устранение проблем с конфигурациями
3.Более быстрая и эффективная разработка

## Задача 2
1) Чем Ansible выгодно отличается от других систем управление конфигурациями?
2) Какой, на ваш взгляд, метод работы систем конфигурации более надёжный — push или pull?
### Ответ 2
1) Ansible выгодно отличается низким порогом входа для новичков, он является декларотивным (описывается что доложно быть сделанно, а не как). Лёгким подключением конфигурацией и кастомной ролью, и SSH-инфраструктуре. 
2) Метод Push более надёжный. Он не требует установки дополнительных серверов, мы вручную или скриптом запускаем процесс применения измененийн а сервере. В режиме pull требуется установки дополнительного сервера, который будет хранить все конфигурации управляемых серверов.

## Задача 3
Установите на личный компьютер:

    VirtualBox,
    Vagrant,
    Terraform,
    Ansible.
### Ответ 3
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/IaaC/img/programm%20PS.png)
## Задача 4
Воспроизведите практическую часть лекции самостоятельно.
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/IaaC/img/Task%204.1.png)
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/IaaC/img/Task%204.2.png)
