### Домашнее задание FreeIPA
Для данного задания я поднял два инстанса в GCP: server и client.

1. Запускаем playbook для установки сервера FreeIPA и открытия портов в firewall: ```ansible-playbook -i hosts server.yml```
2. Запускаем конфигурацию сервера FreeIPA ```ipa-server-install```. Я использовал все значения по умолчанию.
3. Создаем нового пользователя ivan: 
```
kinit admin
ipa user-add ivan --first=Иван --last=Иванов --password
```
4. Задаем ему пароль.
5. Устанавливаем и конфигурируем клиента IPA: ```ansible-playbook -i hosts client.yml```
6. Пробуем зайти на клиента под пользователем ivan:
```
login as: ivan
Server refused our key
Keyboard-interactive authentication prompts from server:
| Password:
End of keyboard-interactive prompts from server
Last login: Fri Feb  7 10:13:49 2020 from 192.162.88.2
-sh-4.2$
```
