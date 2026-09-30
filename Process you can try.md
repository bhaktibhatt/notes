Role Manipulation and Privelege escalation 
Check if user can modify their own or other user's role/permission/privilege or other fields

GPT -
### How to test in a real application

1. Identify different **roles/privilege levels** in the application.
2. Create/use authorized test accounts with different roles.
3. Perform a legitimate role/user-management action and capture the request in **Burp Suite**.
4. Look for parameters related to:
    - `role`
    - `permission`
    - privilege
    - userType
    - `isAdmin`
    - `accessLevel`
    - `group`
    - `tenant/owner`
5. Modify **one sensitive parameter at a time** and try a higher-privileged value or unauthorized value.
6. Send the request and check whether the **server accepts the change**.
7. Verify the actual state after the request — don't rely only on `200 OK`.
8. Re-login / refresh / make a privileged request to confirm whether the new permission actually works.

### What you're trying to prove

```
Normal user
    ↓
Legitimate request
    ↓
Identify privilege-related parameter
    ↓
Modify parameter
    ↓
Server accepts unauthorized value?
    ↓
Privilege actually changes?
    ↓
Higher-privileged functionality works?
```

### Important mindset

Don't focus on specific role names. **Focus on the authorization rule.**

Ask:

> "Can this user **assign/change** a **privilege** that they should not be allowed to control?"

### Evidence

Capture:

- Original request
- Modified request
- Server response
- Before/after role or permission
- Proof that the new privilege actually works

**Key takeaway:**  
A role restriction in the UI is not enough. **Authorization must be enforced server-side.**