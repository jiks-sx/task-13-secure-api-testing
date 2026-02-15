# API Security Testing Lab

## Step 1: Test Authenticated Request
Send request with valid token:

- curl -H "Authorization: Bearer TOKEN" https://api.example.com/users

Verify successful access.

---

## Step 2: Test Without Authentication
Remove token:

- curl https://api.example.com/users

If data is returned → authentication bypass vulnerability.

---

## Step 3: Authorization Testing
Modify resource ID:

- https://api.example.com/users/1001

Change to:

- https://api.example.com/users/1002

If data of another user is accessible → Broken Object Level Authorization.

---

## Step 4: Input Validation Testing
Send malformed data in POST request and observe server response.

---

## Step 5: Rate Limiting Test
Send multiple rapid requests:

- for i in {1..100}; do curl https://api.example.com/users; done

If unlimited requests allowed → rate limiting missing.
