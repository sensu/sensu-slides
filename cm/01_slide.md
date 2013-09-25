<!SLIDE transition=scrollUp>
# Sensu & Chef

## [A love story.]

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

<!SLIDE transition=scrollLeft>
# Cookbooks

github.com/sensu/sensu-chef

github.com/<span class='green'>portertech/chef-monitor</span>

## [LWRPs + Wrapper]
