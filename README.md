### Clickhouse-Vector-Lighthouse Ansible-Playbook-Абрамов Сергей

---

Проект развёртывания инфраструктуры для сбора и анализа логов на основе Clickhouse и Vector и просмотра в Lighthouse.

---


### Installation

Запускаем командой docker compose up файл [docker-compose.yml](https://github.com/smabramov/Ansible-02-hw/blob/b42e046f4445e16b056001c02f90eac9f519acec/playbook/docker-compose.yml)


Вам необходимо создать 3 виртуальных машины.

Для установки использовать дистрибутив CentOS 7.

Для выбора версии и архитектуры замените в файлах group_vars/clickhouse/clickhouse.yml и group_vars/vector/vector.yml соответствующие значения переменных:

```
clickhouse_version: ""

vector_version: ""

```

При необходимости можно изменить пользователей, от имени которых подключается Ansible, в параметре ansible_user в файле /inventory/prod.yml

Выполняем следующие команды:

```
ansible-lint site.yml

ansible-playbook -i ./inventory/prod.yml site.yml --check

ansible-playbook -i ./inventory/prod.yml site.yml --diff

ansible-playbook -i ./inventory/prod.yml site.yml --diff

ansible-playbook -i /inventory/prod.yml site.yml

```