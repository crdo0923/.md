# System Architecture & Workflow 🏛️

**SmartStudy** is built on a clean, modern stack with security and scalability in mind. This document provides a technical overview for developers and administrators.

---

## 🚀 High-Level Architecture

| Component | Technology |
| :--- | :--- |
| **Core Framework** | Vanilla PHP 8.2 (No frameworks) |
| **Database** | MySQL with `mysqli` prepared statements |
| **Frontend** | HTML5, CSS3 (Glassmorphism), Vanilla JavaScript |
| **Real-time** | AJAX Polling (Chat & Notifications) |
| **AI Integration** | Google Gemini API / Groq API |

---

## 👥 User Roles & Access

| Role | Access Level | Entry Point | Key Capabilities |
| :--- | :--- | :--- | :--- |
| **Student** | User | `index.php` | Study, Socialize, Gamification |
| **Admin** | System | `admin_signup.php` | Ban users, moderate content, view analytics |
| **Partner** | Business | `partner_signup_secret.php` | Redeem vouchers, request payouts, manage shop |

---

## 🔄 System Workflow

### 🔓 Authentication Flow
1.  User visits `auth.php` (Login/Register).
2.  Credentials verified via `password_verify()`.
3.  Session started (`$_SESSION['user_id']`).
4.  Redirect to `dashboard.php`.

### 📚 Student Portal
| Page | Role | Key Action |
| :--- | :--- | :--- |
| `dashboard.php` | Central Hub | View stats, quick-start Focus Mode |
| `news_feed.php` | Social Network | Post, Like, Comment, Mention |
| `learning_resources.php` | Knowledge Bank | Upload/Download PDFs, AI Summaries |
| `tasks.php` | Productivity | Urgency Matrix, Exam Mode |
| `study_session.php` | Focus Studio | Distraction-free timers |
| `rewards.php` | Gamification | Redeem XP for real vouchers |

### 🏪 Partner Portal
| Page | Role | Key Action |
| :--- | :--- | :--- |
| `partner_dashboard.php` | Management | Redeem QR codes, request payouts |
| `partner_shop.php` | Cashier Mode | Quick redemption terminal |

### 🛡️ Admin Portal
| Page | Role | Key Action |
| :--- | :--- | :--- |
| `admin.php` | System Control | Ban users, moderate content, approve payouts |

---

## 🗄️ Database Structure

```
Users (id, email, password, xp)
 ├── One-to-Many -> Resources (uploads)
 ├── One-to-Many -> Tasks
 └── One-to-Many -> Posts

Partners (id, name, balance)
 └── One-to-Many -> Redemptions
```

---

## � Security & Data Protection

### Where is my data stored?
*   **Text Data:** Stored in encrypted MySQL tables.
*   **Files:** Secured in `uploads/` directory, paths referenced in DB.

---

### 🔑 Password Protection: Bcrypt

Your password is **never stored in plain text**. We use **Bcrypt**, a one-way cryptographic hashing algorithm.

**How it works:**
1.  Password (e.g., `MyPassword123`) is passed through Bcrypt.
2.  Combined with a unique **salt** and run through multiple **rounds**.
3.  Result: Irreversible hash like `$2y$10$e0xM9kL...`.

**Why it's secure:**
*   **Irreversible:** Cannot be "decrypted" back to original.
*   **Salted:** Two identical passwords produce different hashes.
*   **Slow by Design:** Brute-force attacks are impractical.

---

### 🔒 Message Encryption: AES-256

Private messages are protected using **AES-256** (Advanced Encryption Standard).

**How it works:**
1.  Message encrypted with a secret key before storage.
2.  `"Hey, see you at the library!"` becomes `U2FsdGVkX19...`.
3.  Only the recipient with the correct key can decrypt.

**Why it's secure:**
*   **Military-Grade:** Used by governments and banks worldwide.
*   **End-to-End:** Encrypted on sender's device, decrypted on recipient's.
*   **Admin-Proof:** Even system admins cannot read message content.

---

### 🌐 Secure Connections

All data (login, messages, posts) is protected via **HTTPS (SSL/TLS)** in production, preventing interception in transit.

---

*System Architecture Document | SmartStudy Team | Dec 2025*
