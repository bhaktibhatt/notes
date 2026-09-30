Browser → Burp → Proxy → HTTP history → identify request → Repeater → modify → send → compare → verify

broswer firefox for testing
CA cert added
[[https://medium.com/@maram.raboudi/sniff-intercept-exploit-a-guide-to-web-penetration-testing-with-burp-suite-6be081e66220]]

Burp’s **Proxy tool** then:

1. **Captures requests** sent by your browser.
2. **Displays them** in a readable, editable format.
3. **Lets you modify and forward** them to the target.

This allows you to see everything happening behind the scenes: cookies, parameters, headers, authentication tokens, and more.

For HTTPS, Burp uses its **self-signed SSL certificate** to decrypt the traffic, allowing full visibility into even “secure” data streams.

