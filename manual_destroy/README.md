# Ручной destroy кластера

Это может быть полезным, если планирование и выполнение терраформом происходило на другой машине. 

Для повторного создания кластера терраформом недостаточно будет просто удалить кластер и перезапустить планирование и выполнение, т.к. мы создавали еще и вспомогательные объекты, котороые тоже нужно удалить перед пересозданием (KMS ключ, сервисный аккаунт, группы безопасности, подсеть, сеть). 

На основе [своего скрипта удаления кластера K8s в Yandex Cloud yc_k8s_delete.sh](https://github.com/kodmandvl/wrapper_scripts/blob/main/yc/yc_k8s_delete.sh) сделал скриптик [./yc_k8s_delete_total.sh](./yc_k8s_delete_total.sh) для нашего ручного destroy. 

Запуск: 

```bash
./yc_k8s_list.sh
./yc_k8s_delete_total.sh my-k8s-cluster
```

