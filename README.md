# Домашнее задание к занятию 3 «Резервное копирование»

### Цель задания
В результате выполнения этого задания вы научитесь:
1. Настраивать регулярные задачи на резервное копирование (полная зеркальная копия)
2. Настраивать инкрементное резервное копирование с помощью rsync

------

### Задание 1
- Составьте команду rsync, которая позволяет создавать зеркальную копию домашней директории пользователя в директорию `/tmp/backup`
- Необходимо исключить из синхронизации все директории, начинающиеся с точки (скрытые)
- Необходимо сделать так, чтобы rsync подсчитывал хэш-суммы для всех файлов, даже если их время модификации и размер идентичны в источнике и приемнике.
- На проверку направить скриншот с командой и результатом ее выполнения

------

### Решение 1

Составлена следующая команда:

**rsync -ac --exclude='.*' --progress . /tmp/backup** 

![1](https://github.com/SKA1010/HW_Rsync/assets/125235217/31c9be6e-79d8-448e-be38-817a19d7d5c4)


### Задание 2
- Написать скрипт и настроить задачу на регулярное резервное копирование домашней директории пользователя с помощью rsync и cron.
- Резервная копия должна быть полностью зеркальной
- Резервная копия должна создаваться раз в день, в системном логе должна появляться запись об успешном или неуспешном выполнении операции
- Резервная копия размещается локально, в директории `/tmp/backup`
- На проверку направить файл crontab и скриншот с результатом работы утилиты.

-----

### Решение 2

Написан скрипт, в cron создана задача, каждый день в 15:39 копировать домашнюю директорию пользователя.


![2](https://github.com/SKA1010/HW_Rsync/assets/125235217/7f4ac8ea-1979-4ecc-8776-220e759aad64)

