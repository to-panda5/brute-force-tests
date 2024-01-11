# Test 2 Report

## Conducting the test

1. In Shopmost application register customer with following credentials:
   - Full Name: `Jane Killer`
   - Email: `janekiller@mail.com`
   - Password: `killer`
1. In Burp Suite go to `Intruder` > `Positions` tab.
1. In `Positions` tab:
   - Set `Attack type` to `Sniper`.
   - Set `Target` to `http://[::1]:3000` (localhost or 127.0.0.1 won't work).
   - In the request textfield paste the following content:
        ```txt
        POST /api/customers/sessions HTTP/1.1
        Content-Type: application/json

        {
            "email": "janekiller@mail.com",
            "password": "§ps1§"
        }
        ```
1. Click `Start attack` button and wait for the attack to finish.
1. You should see that the request with password `killer` was successful.

## Results

### Register customer

![register-customer](./test-2-1-register.png)

### Customer dashboard after successful registration

![customer-dashboard](./test-2-2-dashboard.png)

### Prepare test

![prepare-test](./test-2-3-prepare-test.png)

### Test results

![test-results](./test-2-4-results.png)
