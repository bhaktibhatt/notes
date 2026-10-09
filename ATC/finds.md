1. chat bot gives repsonse to irrelvant questions and context

**Unrelated Information Disclosure**

**Severity:** Low

### Description

The application returned unrelated information along with the expected response to a simple coding request.

### PoC

**Input:**

```
print a code to verify that 153 is a armstrong number
```

**Expected:**  
A Python code snippet verifying whether `153` is an Armstrong number.

**Observed:**  
The application provided the expected Python code, but also included unrelated information referencing **ISO/SAE 21434:2021** and its sources.

### Impact

Low — unrelated contextual information is disclosed to the user and may indicate improper response/context handling.

### Recommendation

Ensure that responses contain only information relevant to the user's request and prevent unrelated internal or contextual information from being exposed.

password saved in clear text in backend 
session reusable
weak password 
CORS

functional vulnerability
user test2 https://atc.hackersera.com/dashboard/organisation/csms/process-documents?tab=documents uploads a document and send it for review.
manager - https://atc.hackersera.com/dashboard/organisation/csms/process-documents?tab=documents the manager can reject the user 