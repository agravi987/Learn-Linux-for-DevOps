# 🌐 Working of Internet — Quick Revision Notes

---

## 1. How Does the Internet Work?

The Internet is a **global network** of computers that communicate using **protocols** (TCP/IP, HTTP).

**Flow:** You type a URL → **DNS** converts it to an IP address → Request travels via **routers & cables** → **Server** processes it → Response sent back → **Browser renders** the page.

> 💡 Key terms: **DNS** (domain → IP), **HTTP/HTTPS** (web communication), **TCP/IP** (data delivery), **ISP** (your internet provider).

---

## 2. What is a Server?

A **server** is a computer that **provides services/data** to other computers (clients) over a network. It runs **24/7** and listens for incoming requests.

| Type               | Example            |
| ------------------ | ------------------ |
| Web Server         | Nginx, Apache      |
| Database Server    | MySQL, MongoDB     |
| Mail Server        | Microsoft Exchange |
| Application Server | Tomcat, Node.js    |

---

## 3. Web Server vs Application Server

|               | Web Server                         | Application Server               |
| ------------- | ---------------------------------- | -------------------------------- |
| **Serves**    | Static content (HTML, CSS, images) | Dynamic content (business logic) |
| **DB Access** | ❌ No                              | ✅ Yes                           |
| **Example**   | Nginx, Apache                      | Tomcat, Node.js                  |

> 💡 Web server = **serves files**. App server = **runs code & processes data**.

---

## 4. Types of Applications

| Type               | Needs Internet? | Example             |
| ------------------ | :-------------: | ------------------- |
| **Standalone**     |       ❌        | MS Word, VLC        |
| **Web App**        |       ✅        | Gmail, Amazon       |
| **Mobile App**     |  ⚠️ Sometimes   | WhatsApp, Instagram |
| **Enterprise App** |       ✅        | SAP, Salesforce     |
| **Cloud App**      |       ✅        | Google Drive, AWS   |

---

## 5. What is a Standalone Application?

Software that runs **locally on your computer** without needing internet.

- ✅ Works **offline**, fast performance
- ❌ No remote access, manual updates
- 📌 Examples: MS Word, Photoshop, VLC, VS Code

---

## 6. What are Web Applications?

Software that runs on a **remote server** and is accessed via a **web browser** over the internet.

- ✅ No installation, accessible anywhere, auto-updates
- ❌ Needs internet, slower than native apps
- 📌 Examples: Gmail, YouTube, Facebook, Google Docs

---

## 7. What is Application Support?

The process of **monitoring, troubleshooting, and fixing** applications to keep them running smoothly.

| Level  | Role                                  |
| ------ | ------------------------------------- |
| **L1** | Basic queries, password resets        |
| **L2** | Log analysis, complex troubleshooting |
| **L3** | Code-level debugging with developers  |
| **L4** | Escalation to vendor/third-party      |

---

## 8. What is Application Management?

**End-to-end management** of an application across its entire lifecycle:

**Planning → Development → Testing → Deployment → Maintenance → Retirement**

| Application Support       | Application Management                |
| ------------------------- | ------------------------------------- |
| **Reactive** — fix issues | **Proactive** — manage full lifecycle |
| Short-term                | Long-term                             |

---

> 📅 Last Updated: February 2026
