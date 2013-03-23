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

* Uses exit code to indicate severity.

## 0: OK

## 1: WARNING

## 2: CRITICAL

## >= 3: UNKNOWN or CUSTOM

<!SLIDE center bullets incremental transition=growX>
* Execute a check on a collection* of clients.

* Clients have subscriptions, a list of responsibilities (targets).

* ["load_balancer", "application", "api"]

<!SLIDE center>
# 1:N

<!SLIDE center bullets incremental transition=scrollLeft>
# Alternatively

* Checks can use standalone mode.

* Only scheduled and executed on the client.

* Push\*\*
