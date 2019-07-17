# startWhithAnsible
    Установка Ansible(на Linux) и создание первого сценария.
1. Убедиться что установлен python2 выше верии 2.6 или python3 выше версии 3.5

2. Установка:
    - sudo apt update
    - sudo apt install software-properties-common
    - sudo apt-add-repository --yes ppa:ansible/ansible
    - sudo apt install ansible

3. Настройка конфигурационного файла (ansible.cfg)
    мне не требуется, просто смотрим где по умолчанию лежит inventory файл
    (#inventory      = /etc/ansible/hosts)

4. Добавляем в файл /etc/ansible/hosts все серверы с которыми будем работать
    в моем случае только моя машина, в группе "aservers"
#
    [aservers]
    localhost ansible_connection=local
#
    4.1
        Проверяем, работают ли наши подключения, например используем команду:
        ansible -m ping all
        получаем ответы от серверов, добавленных в hosts

5. создание playbook
    создаем файл *.yml, в нашем случае это
    а) create_file_desk.yml , который создает на рабочем столе файл "new"
    b) telegram_setup.yml , устанавливает и удаляет телеграм
