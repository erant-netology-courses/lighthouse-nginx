# Ansible Role: nginx-lighthouse

Установка и настройка Nginx для работы с Lighthouse — веб-интерфейсом ClickHouse.

## Requirements

- ОС: Ubuntu 20.04/22.04 или Debian 11/12
- Ansible 2.9+

## Role Variables

| Переменная | Значение по умолчанию | Описание |
|-----------|----------------------|----------|
| `nginx_port` | `80` | Порт, на котором Nginx будет слушать |
| `lighthouse_root` | `/var/www/html/lighthouse` | Путь к файлам Lighthouse |
| `nginx_server_name` | `_` | Имя сервера (по умолчанию все) |

## Dependencies

Нет.

## Example Playbook

```yaml
- name: Setup Nginx for Lighthouse
  hosts: lighthouse
  roles:
    - nginx-lighthouse
```

## Inventory

```yaml
lighthouse:
  hosts:
    lighthouse-01:
      ansible_host: 192.168.1.10
      ansible_user: ubuntu
```

## Tags

| Тег | Действие |
|-----|---------|
| `install` | Установка nginx и git |
| `setup-lighthouse` | Деплой конфига и активация сайта |
| `setup-lighthouse-remove-default` | Удаление дефолтного сайта Nginx |

## License

MIT

## Author

@erant-netology-courses