# What is an SSL Certificate? Why are they important?

SSL stands for Secure Sockets Layer; it is the standard technology for keeping an Internet connection secure and safeguarding any sensitive data sent between two systems. The two systems can be server to client (for example, a shopping website and browser) or server to server (for example, an application with personal identifiable information or payroll information).

# What is a TLS Certificate?

TLS stands for Transport Layer Security, which is just an updated, and more secure, version of SSL. TLS is a cryptographic protocol that establishes an encrypted session between applications over the Internet.

TLS certificates usually contain the following information:

- The subject domain name

- The subject organization

- The name of the issuing CA

- Additional or alternative subject domain names, including subdomains, if any

- Issue date

- Expiry date

- The public key (The private key, however, is kept a secret.)

- The digital signature of the CA


# How does TLS work?
TLS uses a combination of symmetric and asymmetric cryptography, as this provides a good negotiation between performance and security when transmitting data securely.

Lean more about TLS handshake:

[Certificate Management | Usage | Security | Encryption Glossary (encryptionconsulting.com)](https://www.encryptionconsulting.com/education-center/what-is-certificate-management/)


# Standard SSL handshake
The communication over SSL always begins with the SSL handshake. The SSL handshake allows the browser to verify the web server, get the public key, and establish a secure connection before the beginning of the actual data transfer.

The following steps are involved in the standard SSL handshake:

- Client Hello

Server communicates with the client using SSL.

This includes the SSL version number, cipher settings, and session-specific data.

- Server Hello

The server responds with a “server hello” message.

This includes the server’s SSL version number, cipher settings, session-specific data, an SSL certificate with a public key, and other information that the client needs to communicate with the server over SSL.

- Authentication

The client verifies the server’s SSL certificate from the CA (Certificate Authority) and authenticates the server.

If the authentication fails, then the client refuses the SSL connection and throws an exception. If the authentication succeeds, then proceed to the next step.

- Decryption

The client creates a session key, encrypts it with the server’s public key and sends it to the server.

If the server has requested client authentication (mostly in server to server communication), then the client sends their own certificate to the server.

- Encryption with Session Key

The server decrypts the session key with its private key and sends the acknowledgement to the client encrypted with the session key.

Thus, at the end of the SSL handshake, both the client and the server have a valid session key which they will use to encrypt or decrypt the original data.


