<!SLIDE transition=scrollUp>
# Sensu & Chef

## [Configuration Management]

<!SLIDE bullets incremental>
* recipe[haproxy]

* recipe[<span class='green'>monitor::haproxy</span>]

<!SLIDE transition=growY>
    @@@
    {
      "id": "check_zombies",
      "command": "check-procs.rb -s Z -w 10 -c 20",
      "subscribers": [
        "linux"
      ],
      "occurrences": 2,
      "additional": {
        "notification": "zombie processes piling up"
      }
    }
