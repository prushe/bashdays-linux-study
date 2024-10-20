# Compilation

## Content table
[Статусы таск](#краткое-пояснение-по-статусам-такс)  
[Минус свап](#минус-свап)  
[Переменные анисбл](#переменные-ансибл)  
[Создание ролей](#создание-ролей)
[Работа со строками](#работа-со-строками-файла)
---

## краткое пояснение по статусам таск ансибл
- **ок:**   
    host == task  изменение не требуется  
- **changed:**  
    host != task  требовались измения. изменения пременены.  
- **skipping:**  
    условие таски не сработало. тот самый when.
 

##  минус свап
- отключить свап  
    `swapоff -a`
- удалить файл  
    `rm /swapfile`  
- выкосить строчку из /etc/fstab  
    `/swapfile none swap sw 0 0`

## приоритеты ансибл
 > Краткая схема приоритетов от низшего к высшему:  
    1. defaults  
    2. group_vars  
    3. vars  
    4. Командная строка, через параметр -e  
   
> Грубо говоря, забиваем переменную сначала в defaults, а потом переопределяем если нужно в infra/group_vars. Все остальное не используем. 


## переменные ансибл

- за получения названия хоста из инвентороя отвечает переменая {{ inventory_hostname }}


## создание ролей 
`ansible-galaxy init <role_name>`

## работа со строками файла
*на примере редактирования fstab*

```
lineinfile:
  path: /etc/fstab
  regexp: '^/swapfile none swap sw 0 0$'
  state: absent
```

`path` - путь до файла  
`regexp` - ругулярка на поиск строки  
`state` - ["Whether the line should be there or not."](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/lineinfile_module.html#parameter-state) должна ли быть строчка там. нет - "absent". дф - "present" ← (default)

