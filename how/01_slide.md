<!SLIDE transition=scrollUp>
# How does it work?

## [What does it do?]

<!SLIDE transition=scrollUp>
# Check

## Result

## V

## Event

# Handler

<!SLIDE bullets transition=scrollUp>
# Check

* Outputs data* to STDOUT or STDERR.

* Uses exit status to indicate severity.

## 0: OK

## 1: WARNING

## 2: CRITICAL

## >= 3: UNKNOWN or CUSTOM

<!SLIDE bullets transition=scrollUp>
# Handler

* Takes action on event data.

* Several types: execute a script, open a socket ...

## [Pipe, TCP, UDP, AMQP, Set]

<!SLIDE center transition=growX>
![badass](../img/badass.png)

<!SLIDE center bullets incremental>
* Execute a check on a collection* of clients.

* Clients have subscriptions, a list of responsibilities (targets).

* ["load_balancer", "application", "api"]

<!SLIDE center>
# 1:N

<!SLIDE center>
# Alternatively

<!SLIDE center bullets incremental transition=scrollLeft>
# Check Standalone Mode

## [I'm my own boss!]

* Only scheduled and executed on the client.

* Push, no execution orchestration.

<!SLIDE center bullets incremental transition=scrollLeft>
# Client Socket

## [localhost:3030]

* Client has a TCP/UDP socket for external input.

* {name: "foo", output: "bar", "status": 1}

<!SLIDE center>
![awwwyeah](../img/awwwyeah.png)

<!SLIDE center bullets transition=scrollLeft>
* Every check result is inspected.

## Non-zero exit status?

## First zero exit status in a series?

## Marked as a metric?

## V

# Event

<!SLIDE center transition=scrollUp>
# Event Data

## [What does it look like?]

<!SLIDE code small>
    @@@
    {
      client: {
        name: "host01",
        address: "10.2.1.11",
        subscriptions: ["linux", "application"],
        timestamp: 1364274222
      },
      check: {
        name: "frontend_https",
        command: "check_http.rb --url https://example.com",
        subscribers: ["application"],
        handlers: ["pagerduty"],
        interval: 60,
        output: "HTTP/1.1 503 Service Temporarily Unavailable",
        status: 2,
        history: [0, 2],
        flapping: false,
        issued: 1364274239,
        executed: 1364274240
      },
      occurrences: 1,
      action: "create"
    }

<!SLIDE center bullets incremental>
# What can we do with it?

## [Event data & HANDLERS]

* Send an email, or ...

<!SLIDE center transition=scrollUp>
![endpoints](../img/endpoints.png)
