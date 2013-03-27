<!SLIDE center transition=scrollLeft>
# Handler Definition

## [What does it look like?]

<!SLIDE code medium transition=scrollUp>
    @@@
    {
      "handlers": {
        "mail": {
          "type": "pipe",
          "command": "mail -s 'sensu' foo@bar.ca"
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "handlers": {
        "pagerduty": {
          "type": "pipe",
          "command": "pagerduty.rb"
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "handlers": {
        "graphite": {
          "type": "tcp",
          "socket": {
            "host": "127.0.0.1",
            "port": 2003
          },
          "mutator": "only_check_output" **
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "handlers": {
        "graylog2": {
          "type": "udp",
          "socket": {
            "host": "127.0.0.1",
            "port": 12201
          },
          "mutator": "gelf"
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "handlers": {
        "logstash": {
          "type": "amqp",
          "exchange": {
            "type": "fanout",
            "name": "sensu_events"
          }
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "handlers": {
        "default": {
          "type": "set",
          "handlers": [
            "pagerduty",
            "logstash"
          ]
        }
      }
    }

<!SLIDE center transition=growY>
![devastator](../img/devastator-oh-yea.png)
