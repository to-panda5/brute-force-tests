# Brute Force Tests

## Note

Due to the limitations (throttling) present in the Burp Suite Community Edition when using the Intruder tool ([source](https://forum.portswigger.net/thread/burp-intruder-bruteforcing-too-slowly-e491c59c)), I had to constrain the complexity level of the test cases. Nevertheless, this is sufficient to demonstrate that the application is not resistant to brute-force attacks.

## Burp Suite setup

1. Download and install [Burp Suite Community Edition](https://portswigger.net/burp/communitydownload).
1. Start Burp Suite.

## Loading payload set

1. Go to `Intruder` > `Payloads` tab.
1. In `Payload sets` section set `Payload type` to `Simple list`.
1. Open [top-100-popular-passwords.txt](./top-100-popular-passwords.txt) file and copy all the content.
1. In `Payload settings [Simple list]` section click `Paste`.

## Performing the tests

1. Test 1 Report - [test-1-report.md](./test-results/test-1/test-1-report.md)
1. Test 2 Report - [test-2-report.md](./test-results/test-2/test-2-report.md)

To create other scenarios just register customer with different email and password from the [top-100-popular-passwords.txt](./top-100-popular-passwords.txt) file, fix the email in the `Intruder` request textfield to match the user and start the attack.

## Summary

As you can see from the test results, the application is not resistant to brute-force attacks. The attacker can easily guess the password of the registered customer. The application should implement some kind of throttling or account lockout mechanism to prevent brute-force attacks.
