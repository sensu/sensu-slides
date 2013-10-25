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
      "interval": 30,
      "additional": {
        "occurrences": 2,
        "notification": "zombie processes piling up"
      }
    }

<!SLIDE>
    @@@ ruby
    sensu_check "check_zombies" do
      command "check-procs.rb -s Z -w 10 -c 20"
      subscribers ["linux"]
      interval 30
      additional(
        :occurrences => 2,
        :notification => "zombie processes piling up"
      )
    end

<!SLIDE transition=scrollLeft>
# Cookbooks

github.com/sensu/sensu-chef

github.com/<span class='green'>portertech/chef-monitor</span>

## [LWRPs + Wrapper]
