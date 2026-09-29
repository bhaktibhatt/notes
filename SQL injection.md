# What is SQL injection?

It is a web security vulnerability that allows an attacker to manipulate a website’s database by inserting malicious SQL code into an app’s input field.

It happens when a web application does not sanitise or validate the user input, where attacker can directly include an SQL query.

# How SQL injection works.

Suppose a website has

input fields - username and password

When a user enters a username, say Alice, and a password, say password

The application builds a Query in the backend like

```jsx
SELECT * FROM users WHERE username ='alice' AND password='alice123';
```

The database reads the SQL statement and finds a matching row, and the login is successful; if not, then the login fails.

If a programmer writes code like

```jsx
"SELECT * FROM users WHERE username ='"+ username + "'"
```

xThe programmer directly inserts user input into the SQL query, and hence the database cannot tell which part of the query is from the programmer and which is from the user; it is only seen as an SQL injection.

Example

here attacker gives input as admin’ - -

The username _admin’—_ gets added to the backend query as given below the _’—_ is comment hence the backend considers rest of the code as comment and returns admin username

![image.png](attachment:1b8c66de-a41e-4c75-850d-7abe55e19b44:image.png)

# Impact of SQLi

Confidentiality - can be used to view sensitive data

Integrity - alter data in the database

Availability - SQLi can be used to delete data

# Types of SQLi

|Type|Key Point|What It Exploits|
|---|---|---|
|**Union-Based SQLi**|Combines attacker-controlled query results with application output|Database result reflection|
|**Error-Based SQLi**|Uses database/application errors to reveal information|Verbose error messages|
|**Boolean-Based Blind SQLi**|Compares different application responses based on true/false conditions|Behavioural differences|
|**Time-Based Blind SQLi**|Uses response delays to infer database behaviour|Execution timing|
|**Out-of-Band (OOB) SQLi**|Uses external interactions such as DNS/HTTP callbacks|External communication|
|**Second-Order SQLi**|Malicious input is stored and executed later in another query|Delayed execution|

![image.png](attachment:bb948113-d6dd-47d9-adde-e6399720e936:image.png)

# **Detecting SQL injection vulnerabilities**

1. Single Quote - (’) , example - `username=’`
2. SQL Syntax Test - `username=’ OR ‘1’=’1`
3. Boolean Condition Test - `OR 1=1` , `OR 1=2 , AND 1=1,`
4. Time Delay Payloads - `SLEEP(5)`
5. Out of Band (OAST) payloads

# SQL injection in parts of Query

1. WHERE clause
2. UPDATE Statements
3. INSERT Statements
4. SELECT Statements
5. ORDER BY clause

### 1. Union-Based SQL Injection

**Purpose:** Determine whether database output can be influenced/reflected.

Important concepts:

- Column-count identification
- Data-type matching
- Metadata enumeration
- Schema discovery
- JSON aggregation
- Multi-tenant database structures

**Keyword:** `UNION`

### 2. Error-Based SQL Injection

Database errors may unintentionally reveal:

- Database version
- Database engine
- Table/query information
- Query fragments
- Backend implementation details

Potential sources of errors:

- Type conversion
- XML parsing
- JSON extraction
- Constraint violations

**Keyword:** **Information leakage**

### 3. Boolean-Based Blind SQLi

No useful database output is directly displayed.

The tester compares application behaviour under different logical conditions.

Look for differences in:

- Response length
- Page structure
- Status/redirect behaviour
- Application behaviour

**Key concept:** **True/False inference**

### 4. Time-Based Blind SQLi

Used when normal responses provide little or no useful information.

The tester observes:

- Response latency
- Consistent timing patterns
- Relationship between conditions and delays

**Key concept:** **Time as a communication channel**

Particularly relevant to:

- APIs
- Financial systems
- Enterprise applications
- Government portals

### 5. Out-of-Band (OOB) SQLi

Used when:

- Output is unavailable
- Errors are suppressed
- Timing is unreliable

The vulnerable database may be induced to make an **external network interaction**.

**Keywords:** DNS callback, HTTP request, external listener, data exfiltration.

### 6. Second-Order SQL Injection

Important sequence:

**Store malicious input → Input appears harmless → Data is reused → Injection executes later**

Common locations:

- User profiles
- Reporting systems
- Admin dashboards
- Background processors

**Key idea:** The vulnerability may not execute at the point where the input is initially submitted.

### Modern SQLi Payload Evolution

Modern attacks can involve:

- Encoding variations
- Case manipulation
- Inline comments
- Logical operator transformations
- Conditional execution
- JSON/XML contexts

**Main takeaway:** Modern SQLi focuses more on **logic abuse and bypassing application controls** than simple injection strings.

### Why Modern SQLi Is Difficult to Detect

- Blind vulnerabilities produce no obvious errors.
- WAFs may reduce obvious attack patterns but do not guarantee security.
- ORM usage does not automatically prevent SQLi.
- Vulnerabilities may exist in internal or less-tested endpoints.
- Second-order attacks can execute far away from the original input.
- APIs may expose different attack surfaces than traditional web forms.

### Defensive Measures

1. **Parameterized queries / prepared statements** — primary defence.
2. **Never concatenate untrusted input into SQL queries.**
3. **Review ORM configuration** — ORM does not automatically mean secure.
4. **Least-privilege database accounts** — application accounts should have only required permissions.
5. **Suppress detailed production errors** — prevent unnecessary information leakage.
6. **Regular security/grey-box testing** — particularly important for logic-based vulnerabilities.
7. **Validate and canonicalise input appropriately.**

### Key Keywords to Remember

**SQLi | Blind SQLi | Union-Based | Error-Based | Boolean-Based | Time-Based | OOB | Second-Order | ORM | WAF | Parameterised Queries | Prepared Statements | Least Privilege | API Security | Data Exfiltration | Input Validation | Canonicalisation | Database Metadata | Logic Abuse**

### One-Line Memory Summary

**Modern SQL Injection = less obvious, more context-aware, often blind, sometimes multi-stage, and increasingly hidden within APIs and application logic.**

SQL injection in 2026 link - [https://medium.com/@jendrala.kumar/advanced-sql-injection-in-2026-modern-payload-techniques-real-world-exploitation-patterns-bae56d04c5f1](https://medium.com/@jendrala.kumar/advanced-sql-injection-in-2026-modern-payload-techniques-real-world-exploitation-patterns-bae56d04c5f1)

Core Idea

- SQL Injection (SQLi) is **not obsolete in 2026**.
- Modern SQLi is often **less visible, more logic-based and harder to detect**.
- Vulnerabilities can exist even when applications use **ORMs, WAFs and error suppression**.
- Commonly hidden in **APIs, reporting endpoints, internal tools and legacy modules**.

### Why SQL Injection Still Exists

- Dynamic SQL query construction
- Misconfigured ORMs
- Legacy code reused in modern applications/microservices
- Insecure API parameter handling
- Second-order injection
- Poor input validation/canonicalisation