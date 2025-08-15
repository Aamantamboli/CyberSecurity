# ☁️ A Guide to Cloud Computing and AWS Security

This guide provides a comprehensive overview of cloud computing concepts and a practical demonstration of security best practices on Amazon Web Services (AWS).
---

## 1. Cloud Computing Fundamentals

### What is Cloud Computing?
Cloud computing is the on-demand delivery of computing services—including servers, storage, databases, networking, software, and analytics—over the internet ("the cloud"). It provides flexibility, scalability, and cost-effectiveness compared to traditional on-premise infrastructure.

### Cloud Service Models
* **Infrastructure as a Service (IaaS):** This model provides virtualized computing resources. You manage the operating system, applications, and middleware, giving you the most control.
    * **Analogy**: Renting an empty building and furnishing it yourself.
    * **Example**: Amazon EC2, Azure Virtual Machines.
* **Platform as a Service (PaaS):** This model provides a platform for developers to build and deploy applications without managing the underlying infrastructure.
    * **Analogy**: Renting an apartment that is already furnished and has utilities set up.
    * **Example**: Google App Engine, Heroku.
* **Software as a Service (SaaS):** This model delivers software applications over the internet on a subscription basis. You only use the software and do not manage anything else.
    * **Analogy**: Renting a fully-equipped hotel room.
    * **Example**: Google Drive, Microsoft 365.

---

## 2. Cloud Security Concepts

The video discusses several key security threats and best practices in a cloud environment:

* **Security Misconfigurations**: A common vulnerability where cloud services are set up incorrectly, such as public S3 buckets, leading to data exposure.
* **Insecure APIs**: APIs with weak authentication can be exploited to access sensitive data.
* **Denial-of-Service (DoS) and DDoS Attacks**: These attacks aim to overwhelm a system, but cloud providers have built-in mitigation tools.
* **Cloud-Powered Botnets**: Attackers can use cloud resources to launch large-scale attacks.
* **The Principle of Least Privilege**: A critical security practice where a user or service is only given the minimum level of access and permissions necessary to perform their job. The practical demonstration in the video focuses on implementing this principle.

---

## 3. Practical Demonstration: AWS User Management

The video provides a hands-on demonstration of setting up secure user access within the AWS console, adhering to the principle of least privilege.

### Step 1: Create a New User
1.  Log in to the AWS Management Console.
2.  Navigate to the **IAM (Identity and Access Management)** service.
3.  Go to **Users** and click **Add users**.
4.  Provide a username and select the access type (e.g., AWS Management Console access).
5.  Set a custom password and require a password change on the first login.

### Step 2: Set Up Multi-Factor Authentication (MFA)
1.  After creating the user, an option to add MFA is presented.
2.  Follow the on-screen instructions to set up a virtual MFA device using an authenticator app (e.g., Google Authenticator) on your phone.
3.  Scan the QR code and enter two consecutive MFA codes to complete the setup.

### Step 3: Create a Custom Policy
1.  Navigate to **Policies** in the IAM dashboard.
2.  Click **Create policy**.
3.  Use the **JSON editor** to write a custom policy that grants specific permissions. In the video, the user writes a policy to grant full access to EC2 services.
4.  Name the policy and save it.

### Step 4: Attach the Policy to the User
1.  Go back to the user you just created.
2.  Click on the **Permissions** tab and select **Add permissions**.
3.  Choose **Attach existing policies directly**.
4.  Search for the custom policy you just created and attach it to the user.
5.  The user will now only have access to EC2 services and nothing else, demonstrating the principle of least privilege.

---
