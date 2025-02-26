Nextauth is a library that lets you do authentication in Nextjs.
	https://auth0.com/
	https://clerk.com/


### why does nextauth done not use jwt+localstorage
Using **localStorage** for authentication is a bad practice due to **security vulnerabilities (XSS, token theft, manual expiry handling, etc.)**. Instead, NextAuth uses **secure HTTP-only cookies**, which are **automatically managed by the browser** and **protected from client-side JavaScript attacks**.

**Why NextAuth.js Uses Secure HTTP-Only Cookies**

  

NextAuth.js **stores session tokens inside HTTP-only cookies** instead of localStorage, solving the above issues.

1. **🔒 Protection Against XSS**

• Cookies are **HTTP-only**, meaning **JavaScript cannot access them**.

• Even if an attacker injects JS, they **cannot steal authentication tokens**.

2. **🔄 Automatic Expiry & Refresh**

• Cookies have built-in expiration handling.

• NextAuth.js can **automatically refresh tokens** without requiring manual API calls.

1. **🛡️ CSRF Protection**

• Since cookies are **automatically sent with every request**, they integrate with built-in CSRF protection mechanisms.

• **No need for manual headers like Authorization: Bearer <token>**.

2. **📦 Simpler Backend Handling**

• Cookies are automatically sent with requests, so the backend can simply check them without extra logic.

• Works **seamlessly with Next.js API routes**.


 **How NextAuth.js Uses Cookies Instead of LocalStorage**

• NextAuth stores session tokens **inside an HTTP-only, secure cookie**.

• Example flow:

1. User logs in → NextAuth creates a sessionand sets it in a secure cookie.

2. The cookie is automatically sent with every request (no manual headers needed).

3. The server reads the session from the cookie and validates the user.

4. When the session expires, NextAuth can refresh it automatically


**Authentication Providers in NextAuth.js**

  

NextAuth.js allows users to **sign in using multiple providers**:

  

🔹 **OAuth Providers (Google, GitHub, Twitter, etc.)**

🔹 **Custom OAuth Providers**

🔹 **Email Sign-In (Magic Link)**

🔹 **Credentials-based Authentication (Custom Login Forms)**

  

👉 **For credentials authentication (signIn("credentials")), NextAuth.js still does NOT store tokens in localStorage—it always uses secure cookies.**

[[Credentials]]