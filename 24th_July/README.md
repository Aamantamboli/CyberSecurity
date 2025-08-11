# 🛡️ Session, Cookies, and Session Hijacking

---

## 🔑 What is a Cookie?

Cookies are small pieces of data stored on the client’s browser by a website. They help remember user preferences, session tokens, and other information to maintain a smooth browsing experience.

- Stored on the client (browser)  
- Sent with every HTTP request to the server  
- Commonly used to store session IDs  

---

## 🔐 What is a Session?

A session is a way for a server to remember a user’s state and data across multiple requests. Sessions are stored on the server, and the client holds a unique session ID (usually in a cookie) to identify their session.

- Stored on the server  
- Identified via session ID sent in cookies  
- Keeps users logged in and tracks activity  

---

## 🚨 What is Session Hijacking?

Session hijacking is an attack where an attacker steals or guesses a valid session ID (usually via cookies) to impersonate a user without knowing their password.

### How attackers hijack sessions:

- Stealing cookies via Cross-Site Scripting (XSS)  
- Sniffing unencrypted network traffic (no HTTPS)  
- Predicting weak session IDs  
- Man-in-the-middle (MITM) attacks  

---

## 🎯 How to Perform Session Hijacking on OWASP Juice Shop

### Step 1: Understand Session Management  
- Log in to OWASP Juice Shop.  
- Open browser developer tools → Application → Cookies.  
- Find the session token cookie (commonly named `token`).

### Step 2: Capture the Session Token  
- Use proxy tools like **Burp Suite** or **OWASP ZAP** to intercept requests and capture tokens.  
- Or copy the token directly from the browser cookie storage.

### Step 3: Use the Stolen Token  
- Replace your browser or proxy’s session token with the stolen token.  
- Access the Juice Shop to act as the hijacked user.

### Step 4: Exploit Session Hijacking Challenges  
- Juice Shop contains challenges related to session hijacking.  
- Use stolen tokens to access other users’ data or complete specific challenges.

---

## ⚠️ Why Is Session Hijacking Dangerous?

| Risk               | Explanation                                    |
| ------------------ | ----------------------------------------------|
| Unauthorized Access| Attacker accesses user accounts without login |
| Data Theft         | Sensitive data can be stolen                    |
| Privilege Escalation| Attackers may gain higher access                |
| Complete Account Takeover | Attacker controls the account entirely     |

---

## 🛡️ How to Protect Against Session Hijacking

| Prevention Tip           | How It Helps                              |
|--------------------------|------------------------------------------|
| Use HTTPS everywhere     | Encrypts traffic, protects cookies       |
| Use secure, HttpOnly cookies | Prevents JavaScript access to cookies  |
| Regenerate session IDs on login | Prevents fixation attacks            |
| Set short session timeouts| Limits window for attackers               |
| Implement multi-factor authentication | Adds extra verification layer    |

---
