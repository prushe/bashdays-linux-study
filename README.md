# bashdays-linux-study
Отчет по урокам bashdays

# #s1e0


### поднял две машины stage и production выдал статический айпи 192.168.0.11 и 192.168.0.12 соответственно


### разрешил доступ по ссш к руту по паролю
```
PasswordAuthentication yes
PermitRootLogin  yes
```

### ssh-keygen сгенерировал ключ закинул на сервки 
```
scp id_rsa.pub root@192.168.0.11:~/.ssh/authorized_keys
scp id_rsa.pub root@192.168.0.12:~/.ssh/authorized_keys
```


### рапретил доступ к руту по паролю
```
PasswordAuthentication no
PermitRootLogin prohibit-password
```
