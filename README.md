# rabbitmq

[![Build Status](https://drone.osshelp.ru/api/badges/ansible/rabbitmq/status.svg)](https://drone.osshelp.ru/ansible/rabbitmq)

The role installs and configures RabbitMQ.

## Usage (example)

### Minimal

```yaml
    - role: rabbitmq
```

### Configure mode + custom parameters

Don't set too old versions in `rabbitmq_packagecloud_version` variable, they won't work.

```yaml
    - role: rabbitmq
      rabbitmq_setup: configure
      rabbitmq_type: packagecloud
      rabbitmq_packagecloud_version: 3.7.*
      rabbitmq_plugins: "rabbitmq_management"
      rabbitmq_envs:
        NODENAME: rabbitmq1
        NODE_IP_ADDRESS: 0.0.0.0
        NODE_PORT: 5672
```

## Available parameters

| Param | Description |
| -------- | -------- |
| `rabbitmq_setup` | Default: `full`. See [OSSHelp KB article](https://oss.help/kb4895) |
| `rabbitmq_type` | Default: `distr`. Installation type: distr version or latest from packagecloud |
| `rabbitmq_plugins` | Comma separated RabbitMQ plugins |
| `rabbitmq_envs`| Environment variables for RabbitMQ. Dictionary: `NAME: VALUE` |
| `rabbitmq_packagecloud_version`| RabbitMQ version for packagecloud installation |

## Useful links

- [Official documentation](https://www.rabbitmq.com/documentation.html)
- [Our articles](https://rm.osshelp.ru/projects/support-servers/search?utf8=%E2%9C%93&q=rabbitmq&commit=%D0%9F%D1%80%D0%B8%D0%BD%D1%8F%D1%82%D1%8C&all_words=&titles_only=&scope=&kb_articles=1)

## TODO

- cluster support
- auth settings
- add focal support for packagecloud

## License

GPL3

## Author

OSSHelp Team, see <https://oss.help>
