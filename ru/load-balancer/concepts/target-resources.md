# Целевые ресурсы и группы 

Балансировщик распределяет нагрузку между облачными ресурсами, объединенными в *целевые группы*. Один облачный ресурс нельзя сделать целевым для нескольких балансировщиков.

*Целевой ресурс* определяется двумя параметрами: идентификатором подсети и внутренним IP-адресом ресурса. Целевые ресурсы одной группы должны находиться в одной облачной сети. В пределах одной зоны доступности все целевые ресурсы должны быть подключены к одной подсети. Максимальное количество ресурсов в целевой группе — 254.

Целевые ресурсы должны принимать трафик на порту с тем же номером, что указан в конфигурации обработчика.

## Подключенная целевая группа {#attached-target-group}

Подключенная целевая группа — это группа целевых ресурсов, [подключенная](../operations/target-group-attach.md) к балансировщику. К каждому балансировщику можно подключить только одну целевую группу. После подключения целевой группы балансировщик начнет проверять состояние целевых ресурсов и сможет распределять нагрузку между входящими в группу ресурсами.