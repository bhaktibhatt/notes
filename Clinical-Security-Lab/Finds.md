1. The user can be created with role:normal  only in frontend but backend is not protected when request is send to repeater and role is changed to admin its is giving 200 response.

2. Email of user is valid without domain like test@t is valid no need for .com ? -> not so severe

3. in search bar if searched for something the query executed is shown at the bottom

4. [[SQL injection]] in search bar

5. verbose error

6. [[Html Injection]] in patient records -
   PUT /api/patients/3 HTTP/1.1
   Host: 192.168.1.43:5000

7. Stored XSS on message and Report 
   POST /api/messages HTTP/1.1
   Host: 192.168.1.43:5000

8. file extension bypass  (File Upload)-
   only png is allowed but it can be bypassed. 
   POST /api/uploads HTTP/1.1
   Host: 192.168.1.43:5000