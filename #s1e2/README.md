# bashdays-linux-study

Отчет по урокам bashdays

# #s1e2

1. в инвентаре создал прод.ини стэйдж.ини 


2. в прод.ини прописал адрес и юзера
```
[web]

prd-wb-f ansible_host=192.168.0.12 ansible_user=root
```

3. в стэйдж.ини прописал адрес и юзера
```
[web]

stg-wb-f ansible_host=192.168.0.11 ansible_user=root
```

4. проверил что ансибл коректно загружает инвентарь
```
ansible-inventory --graph -i inventory/production.ini 

ansible-inventory --graph -i inventory/stage.ini
```
