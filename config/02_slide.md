<!SLIDE center transition=scrollUp>
# Check Definition

## [How does one look?]

<!SLIDE code medium transition=scrollUp>
    @@@
    {
      "checks": {
        "foo": {
          "command": "echo -n foo && exit 1",
          "subscribers": [
            "bar"
          ],
          "interval": 30
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "checks": {
        "haproxy_services": {
          "command": "check-haproxy.rb -w 70 -c 50",
          "subscribers": [
            "load_balancer"
          ],
          "interval": 30
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "checks": {
        "haproxy_services": {
          "command": "check-haproxy.rb -w 70 -c 50",
          "subscribers": [
            "load_balancer"
          ],
          "interval": 30,
          "handlers": ["irc", "pagerduty"]
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "checks": {
        "haproxy_services": {
          "command": "check-haproxy.rb -w 70 -c 50",
          "subscribers": [
            "load_balancer"
          ],
          "interval": 30,
          "handlers": ["irc", "pagerduty"],
          "custom": {
            "nested": "attribute"
          }
        }
      }
    }

<!SLIDE code medium transition=scrollUp>
    @@@
    {
      "checks": {
        "foo": {
          "type": "metric",
          "command": "echo bar 42 `date +%s`",
          "subscribers": [
            "bar"
          ],
          "interval": 10
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "checks": {
        "foo": {
          "type": "metric",
          "command": "echo bar 42 `date +%s`",
          "standalone": true,
          "interval": 10
        }
      }
    }

<!SLIDE code medium>
    @@@
    {
      "checks": {
        "haproxy_metrics": {
          "type": "metric",
          "command": "haproxy-metrics.rb",
          "standalone": true,
          "interval": 10,
          "handlers": ["graphite"]
        }
      }
    }
