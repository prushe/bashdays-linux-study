# bashdays-linux-study

Отчет по урокам bashdays

# #s1e1

1. установил ансибл
```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
ansible --version
```

2. создал структуру папок и файлов для работы с ансибл
```
ll administration/
total 28
drwxr-xr-x 6 root root 4096 Aug 28 21:57 ./
drwx------ 9 root root 4096 Aug 28 21:09 ../
-rw-r--r-- 1 root root  248 Aug 28 21:46 ansible.cfg
drwxr-xr-x 2 root root 4096 Aug 28 21:41 group_vars/
drwxr-xr-x 2 root root 4096 Aug 28 21:41 inventory/
-rw-r--r-- 1 root root    0 Aug 28 21:42 production.yml
drwxr-xr-x 2 root root 4096 Aug 28 21:41 roles/
-rw-r--r-- 1 root root    0 Aug 28 21:42 stage.yml
drwxr-xr-x 2 root root 4096 Aug 28 21:41 templates/
```

3. поправил конфиг 
```
[defaults]
host_key_checking  = false
fact_caching = jsonfile
fact_caching_connection = /root/administration/facts
# library = library
gather_facts = true
interpreter_python = auto

[connection]
pipelining = True

[ssh_connection]
pipelining = True
```

4. подкинул пубичные ключи от мастер машины на хосты
*заблаговременно открыл доступ для входа по паролю. после закрыл его*
* ssh-keygen
* ssh-copy-id root@192.168.0.11
* ssh-copy-id root@192.168.0.12  
