<!SLIDE center transition=scrollLeft>
# Client Definition

## [How does one look?]

<!SLIDE code medium transition=scrollUp>
    @@@
    {
      "client": {
        "name": "host02",
        "address": "10.2.1.12",
        "subscriptions": [
          "linux",
          "load_balancer"
        ],
        "custom": {
          "nested": "attribute"
        }
      }
    }
