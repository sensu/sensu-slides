<!SLIDE center transition=scrollLeft>
# Connection Definition

## [Let's wire it up!]

<!SLIDE code medium transition=scrollUp>
    @@@
    {
      "rabbitmq": {
        "host": "10.2.1.2",
        "port": 5672,
        "vhost": "/sensu",
        "user": "sensu",
        "password": "secret"
      }
    }

<!SLIDE code medium transition=scrollUp>
    @@@
    {
      "redis": {
        "host": "10.2.1.3",
        "port": 6379
      }
    }
