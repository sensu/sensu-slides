<!SLIDE center transition=scrollLeft>
# Client Definition

## [How does one look?]

<!SLIDE code medium transition=scrollUp>
    @@@
    {
      "client": {
        "name": "host01",
        "address": "10.2.1.11",
        "subscriptions": [
          "linux",
          "load_balancer"
        ],
        "custom": {
          "nested": "attribute"
        }
      }
    }
