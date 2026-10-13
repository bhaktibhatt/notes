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
manager - https://atc.hackersera.com/dashboard/organisation/csms/process-documents?tab=documents the manager can approve or reject, the draft uploaded by test2, the reject message should be visible to test2 but it is not where is the msg stored is also not clear.


managers should be able to see what engineers are under them and what  


## Ticket 1

**Title:** Chatbot responds to out-of-scope queries (e.g., Armstrong number code)

**Description:**  
The chatbot on atc.hackersera.com responds to irrelevant questions and context. When prompted to write code for an Armstrong number, it gives a response for that code. The chatbot is supposed to assist only with context-aware guidance for ISO/SAE 21434 compliance, CSMS and SUMS, and should not answer queries outside this scope.

---

## Ticket 2

**Title:** Manager’s rejection message not visible to the engineer on rejected document

**Description:**  
User test2 uploads a document and sends it for review on the Process Documents page ([https://atc.hackersera.com/dashboard/organisation/csms/process-documents?tab=documents](https://atc.hackersera.com/dashboard/organisation/csms/process-documents?tab=documents)). The manager can approve or reject the draft uploaded by test2 from the same page. When the manager rejects the draft, the rejection message should be visible to test2, but it is not. It is also unclear where the message is stored. Two separate logins (test2 and manager) were used to check whether test2 receives the approved or rejected message, but it is not clearly visible.

---

## Ticket 3

**Title:** Manager–engineer hierarchy not visible in the application

**Description:**  
Managers should be able to see which engineers are under them. It should also be clearly specified which engineers are under which manager




