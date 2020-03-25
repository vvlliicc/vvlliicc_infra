
1. Подключение к someinternalhost в одну команду
```bash
ssh -i ~/.ssh/appuser -J 34.90.137.138 10.164.0.7
```
2. Подключение одной командой ssh someinternalhost
Необходимо добавить в файл .ssh/config
```bash
Host bastion
StrictHostKeyChecking no
UserKnownHostsFile /dev/null
Hostname 34.90.137.138
User appuser
AddKeysToAgent yes
IdentityFile ~/.ssh/appuser

Host someinternalhost
StrictHostKeyChecking no
UserKnownHostsFile /dev/null
HostName 10.164.0.7
ProxyJump appuser@bastion
User appuser
AddKeysToAgent yes
IdentityFile ~/.ssh/appuser

```
3.

bastion_IP = 34.90.137.138

someinternalhost_IP = 10.164.0.7



### Home work № 4
testapp_IP = 34.91.217.122
testapp_port = 9292
