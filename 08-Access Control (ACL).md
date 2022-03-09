# Access Control (ACL)

An access control list (ACL) contains rules that grant or deny access to certain digital environments. There are two types of ACLs:

- Filesystem ACLs━filter access to files and/or directories. Filesystem ACLs tell operating systems which users can access the system, and what privileges the users are allowed.

- Networking ACLs━filter access to the network. Networking ACLs tell routers and switches which type of traffic can access the network, and which activity is allowed.

Originally, ACLs were the only way to achieve firewall protection. Today, there are many types of firewalls and alternatives to ACLs. However, organizations continue to use ACLs in conjunction with technologies like virtual private networks (VPNs) that specify which traffic should be encrypted and transferred through a VPN tunnel.

### Reasons to use an ACL:

1. Traffic flow control.

2. Restricted network traffic for better network performance.

3. A level of security for network access specifying which areas of the server/network/service can be accessed by a user and which cannot.

4. Granular monitoring of the traffic exiting and entering the system.

### How ACL Works

A filesystem ACL is a table that informs a computer operating system of the access privileges a user has to a system object, including a single file or a file directory. Each object has a security property that connects it to its access control list. The list has an entry for every user with access rights to the system.

Typical privileges include the right to read a single file (or all the files) in a directory, to execute the file, or to write to the file or files. Operating systems that use an ACL include, for example, Microsoft Windows NT/2000, Novell’s Netware, Digital’s OpenVMS, and UNIX-based systems.

When a user requests an object in an ACL-based security model, the operating system studies the ACL for a relevant entry and sees whether the requested operation is permissible.

Networking ACLs are installed in routers or switches, where they act as traffic filters. Each networking ACL contains predefined rules that control which packets or routing updates are allowed or denied access to a network.

Routers and switches with ACLs work like packet filters that transfer or deny packets based on filtering criteria. As a Layer 3 device, a packet-filtering router uses rules to see if traffic should be permitted or denied access. It decides this based on source and destination IP addresses, destination port and source port, and the official procedure of the packet.

### Review, Research, and Discussion

1. **When is Basic Authorization used vs. Bearer Authorization?**

   The Basic and Digest authentication schemes are dedicated to the authentication using a username and a secret. The Bearer authentication scheme is dedicated to the authentication using a token.

   Instead of having your user send their actual credentials to your server on every single request (like they would with Basic Auth, where a user sends their username/password to the server for each request), with OAuth you first exchange your user credentials for a 'token', and then authenticate users based on this token.

2. **What does the JSON Web Token package do?**

   Each JWT contains encoded JSON objects, including a set of claims. JWTs are signed using a cryptographic algorithm to ensure that the claims cannot be altered after the token is issued.

3. **What considerations should we make when creating and storing a SECRET?**

   a. Differentiate Between Secrets and Identifiers.<br>
   b. Establish a Circle of Trust.<br>
   c. Encrypt Data Using a KMS.<br>
   d. Detect Unauthorized Access.<br>

---

### Vocabulary Terms

| Term           | Defenition                                                                                                                                                                                                                                                                                                                                                                                                                           |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| encryption     | a way of scrambling data so that only authorized parties can understand the information. In technical terms, it is the process of converting human-readable plaintext to incomprehensible text, also known as ciphertext.                                                                                                                                                                                                            |
| token          | a highly secure format used to transmit sensitive information between two parties in a compact and self-contained manner. Tokens are often used to strengthen authentication processes,                                                                                                                                                                                                                                              |
| Bearer         | The name “Bearer authentication” can be understood as “give access to the bearer of this token.” The bearer token is a cryptic string, usually generated by the server in response to a login request.                                                                                                                                                                                                                               |
| Secret         | every application, script, automation tool and other non-human identity relies on some form of privileged credential to access other tools, applications and data. These non-human privileged credentials are often called “secrets” and refer to a private piece of information that acts as a key to unlock protected resources or sensitive information in tools, applications, containers, DevOps and cloud-native environments. |
| JSON Web Token | a proposed Internet standard for creating data with optional signature and/or optional encryption whose payload holds JSON that asserts some number of claims. The tokens are signed either using a private secret or a public/private key.                                                                                                                                                                                          |

---

---

### RBAC: Role Based Access Control

It is an approach to restricting system access to authorized users. It is an approach to implement mandatory access control (MAC) or discretionary access control (DAC).

ALright alright alright, let's use simpler terms so we can understand what is going on here.

One can simply define a Role Based Access Control as a policy-neutral access-control mechanism defined around roles and privileges. The components of RBAC such as role-permissions, user-role and role-role relationships make it simple to perform user assignments. RBAC can be used to facilitate administration of security in large organizations with hundreds of users and thousands of permissions. Although RBAC is different from MAC and DAC access control frameworks, it can enforce these policies without any complication.

Within an organization, roles are created for various job functions. The permissions to perform certain operations are assigned to specific roles. Members or staff (or other system users) are assigned particular roles, and through those role assignments acquire the permissions needed to perform particular system functions. Since users are not assigned permissions directly, but only acquire them through their role (or roles), management of individual user rights becomes a matter of simply assigning appropriate roles to the user's account; this simplifies common operations, such as adding a user, or changing a user's department.

Role based access control interference is a relatively new issue in security applications, where multiple user accounts with dynamic access levels may lead to encryption key instability, allowing an outside user to exploit the weakness for unauthorized access. Key sharing applications within dynamic virtualized environments have shown some success in addressing this problem.

Three primary rules are defined for RBAC:

- Role assignment: A subject can exercise a permission only if the subject has selected or been assigned a role.
- Role authorization: A subject's active role must be authorized for the subject. With rule 1 above, this rule ensures that users can take on only roles for which they are authorized.
- Permission authorization: A subject can exercise a permission only if the permission is authorized for the subject's active role. With rules 1 and 2, this rule ensures that users can exercise only permissions for which they are authorized.

Additional constraints may be applied as well, and roles can be combined in a hierarchy where higher-level roles subsume permissions owned by sub-roles.
With the concepts of role hierarchy and constraints, one can control RBAC to create or simulate lattice-based access control (LBAC).

---

### Resources

[Access Control List (ACL)](https://www.imperva.com/learn/data-security/access-control-list-acl/)<br>
[difference between OAuth based and Token based authentication?](https://stackoverflow.com/questions/34784644/what-is-the-difference-between-oauth-based-and-token-based-authentication)<br>
[Best Practices for Container Secrets Management](https://thenewstack.io/8-best-practices-for-container-secrets-management/)<br>
[role-based access control (RBAC)](<https://www.techtarget.com/searchsecurity/definition/role-based-access-control-RBAC#:~:text=Role-based%20access%20control%20(RBAC)%20is%20a%20method%20of,doesn't%20pertain%20to%20them.>)<br>
