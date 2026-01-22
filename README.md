# SmartStudy Platform 🎓

**SmartStudy** is a premier academic productivity and social ecosystem designed to transform how students learn, connect, and excel. By blurring the lines between a Learning Management System (LMS), a productivity suite, and a social network, SmartStudy provides a holistic environment for academic success.

---

## 🚀 Key Features at a Glance

| Feature | Description |
| :--- | :--- |
| **🧠 Integrated Productivity** | Complete task management, focus timers, and intelligent scheduling in one cohesive dashboard. |
| **🌍 Social Learning** | A dedicated academic news feed for discourse, resource sharing, and community engagement. |
| **🤖 AI-Powered** | Embedded AI tutors (Gemini/Groq) for instant help, summarization, and study planning. |
| **🔐 Secure Access** | Robust 2FA (Two-Factor Authentication), Google Auth integration, and encrypted privacy. |
| **🎮 Gamified Growth** | Earn XP, level up, reach the leaderboards, and redeem real-world rewards for studying. |
| **🎨 Chameleon Theme** | A dynamic styling engine that adapts the UI for optimal visual comfort and aesthetics. |
| **️ Unified Feedback** | A seamless system for reporting bugs, suggesting features, and tracking resolution status. |
| **📚 Resource Library** | A community-driven repository to upload, share, and discover notes, slides, and videos. |

---

## 📅 Project Timeline

View the detailed development schedule here: **[📂 View Project Gantt Chart & Schedule](GANTT_CHART.md)**

### 🎓 About the Project
Learn more about our mission, vision, and the team behind SmartStudy: **[👥 About SmartStudy](ABOUT.md)**

---

## 📖 User Manual: Page by Page

Here is what you can do on each section of the SmartStudy platform:

### 1. 🔐 Authentication & Security (`auth.php`, `auth_2fa.php`)
Your secure gateway to the platform.
*   **Two-Factor Authentication (2FA):** Secure your account with email-based OTP verification.
*   **Robust Verification:** Mandatory email verification ensures a secure community. New accounts (including Google sign-ups) must confirm their email before access.
*   **Student ID Verification:** Automated OCR scanning of PLMun Student IDs to instantly verify enrollment and unlock student-exclusive rewards.
*   **Smart Feedback:** Interactive "Verifying..." status screens and intuitive redirects guide you smoothly.
*   **Google Integration:** Seamlessly connect your Google account with enforced verification for maximum security.

### 2. 🏠 Dashboard (`dashboard.php`)
Your central command center for the day.
*   **Daily Motivation:** Start your day with a curated inspirational quote.
*   **Focus Studio:** Integrated timer with **"Smart Player"** (lo-fi/ambient music), session blocking, and modes (Standard, Deep Focus, Exam Mode).
*   **Study Analytics:** Visual breakdowns of your study habits including a **7-Day History Chart** and **Subject Distribution** graphs.
*   **At a Glance:** View your immediate next tasks and deadlines.
*   **Gamification Stats:** Check your current Level, XP progress, and Rank.

### 3. 📰 StudyFeed (`news_feed.php`)
The social heartbeat of the campus.
*   **Share Updates:** Post questions, insights, or achievements with rich text and media (images/videos).
*   **Engage:** Like, comment, and reply to peers to foster discussion.
*   **Trending:** See what topics are hot in the community.
*   **Mentions:** Tag friends using `@username` to bring them into the conversation.

### 4. 📚 Learning Resources (`learning_resources.php`)
A collaborative library for academic materials.
*   **Upload & Share:** Contribute your own notes, cheat sheets, or helpful videos.
*   **Smart Search & Filter:**
    *   **Subject Filters:** Quickly narrow down by Math, Science, IT, and more.
    *   **Search Bar:** Find specific topics instantly.
    *   **My Uploads:** Toggle to view only the resources *you* have contributed.
*   **AI Summaries:** Use the **Magic Wand** button on any text resource to get an instant AI-generated summary of its contents.

### 5. ✅ Tasks (`tasks.php`)
Master your schedule with advanced task management.
*   **Urgency Matrix:** Automatically sorts tasks into "Do First," "Schedule," "Delegate," and "Delete" based on priority.
*   **Views:** Switch between a Kanban Board view or a traditional List view.
*   **Exam Mode:** Flag high-stakes tasks as exams for special visibility.
*   **Deadlines:** Set due dates to keep yourself accountable.

### 6. 💬 Messaging (`messaging.php`)
Stay connected with your study groups.
*   **Direct Messages:** Private real-time chat with friends.
*   **Group Chats:** Collaborate with your entire class or project team.
*   **Voice Clips:** Record and send voice messages directly in the chat with a seamless, integrated visualizer.
*   **File Sharing:** Send documents and images directly within the chat.

### 7. 📱 Mobile Experience (`mobile.php`)
Optimized access for mobile devices.
*   **Sandbox Mode:** Experience core features like the Task List and Focus Timer in a demo environment without logging in.
*   **Lobby:** Learn about the app and get directed to the full desktop experience for advanced analytics.

### 8. 👤 Profile (`profile.php`)
Your academic identity.
*   **Stats Card:** innovative "RPG-style" stats card showing your attributes (Focus, Consistency, etc.).
*   **Virtual Pets:** Adopt and feed a digital companion that levels up as you maintain your study streaks.
*   **Activity History:** A timeline of your posts and contributions.
*   **Customization:** Update your bio, profile photo, and banner.

### 9. 🏆 Rewards & Leaderboards (`rewards.php`, `leaderboards.php`)
Make studying fun.
*   **Leaderboards:** See how you rank against the entire campus or just your friends.
*   **Rewards:** Redeem your hard-earned XP for exciting rewards.

### 10. 🐛 Bug Reporting
Have something to say?
*   **Unified Reporting:** Use the "Report Issue" widget (bottom right) to send Bug Reports, Suggestions, or General Feedback.
*   **Track Status:** Receive notifications when admins resolve your reports or review your suggestions.
*   **Context Aware:** The system automatically captures screenshots (with permission) to help developers fix bugs faster.

---

## 🤖 AI Capabilities

SmartStudy is built with AI at its core:
*   **Global Chat:** Click the brain/bulb icon anywhere to summon your AI tutor.
*   **AI Proctoring:** Optional vision-based monitoring for "Exam Mode" sessions that analyzes engagement and ensures academic integrity using camera snapshots or video.
*   **Content Generation:** Ask the AI to draft study plans or explain complex topics.
*   **Summarization:** Digest long resources in seconds.
*   **Provider Choice:** Switch between **Google Gemini** (default) or **Groq** for ultra-fast responses (configurable in Settings).

---

## 🔐 Security & Privacy

Your data is secure with SmartStudy. We use industry-standard encryption and hashing to protect your information.

### Database Snapshot Example
Here is how your sensitive data looks in our database. Even if someone gains access, your personal messages and passwords remain unreadable.

| User ID | Username | Password (Hash) | Message Content (E2E Encrypted) |
| :--- | :--- | :--- | :--- |
| **101** | `ricardo` | `$2y$10$e0xM9...` (Bcrypt Hash) | `U2FsdGVkX1+...` (Unreadable) |
| **102** | `patrick` | `$2y$10$9aB7z...` (Bcrypt Hash) | `U2FsdGVkX19...` (Unreadable) |

---

### 🔑 How We Protect Your Password: **Bcrypt**

Your password is **never stored in plain text**. Instead, we use **Bcrypt**, a one-way cryptographic hashing algorithm.

**How it works:**
1.  When you register, your password (e.g., `MyPassword123`) is passed through the Bcrypt algorithm.
2.  Bcrypt combines your password with a unique, randomly generated **salt** (random data) and runs it through multiple **rounds** of computation.
3.  The result is a fixed-length, irreversible hash like `$2y$10$e0xM9kL...`.

**Why it's secure:**
*   **Irreversible:** The hash cannot be "decrypted" back to the original password. Even if a hacker steals the database, they only see gibberish.
*   **Salted:** Each password has a unique salt, so two users with the password "123456" will have completely different hashes.
*   **Slow by Design:** Bcrypt is intentionally slow, making brute-force attacks (trying millions of passwords) impractical.

---

### 🔒 How We Protect Your Messages: **AES-256**

Your private messages are protected using **AES-256** (Advanced Encryption Standard with a 256-bit key), the gold standard for symmetric encryption.

**How it works:**
1.  When you send a message, it is encrypted using a secret key before being stored.
2.  The message `"Hey, see you at the library!"` becomes an unreadable string like `U2FsdGVkX19...`.
3.  Only the intended recipient, who possesses the correct key, can decrypt and read the original message.

**Why it's secure:**
*   **Military-Grade:** AES-256 is used by governments and banks worldwide. It would take billions of years to crack with current technology.
*   **End-to-End (E2E):** Messages are encrypted on your device and only decrypted on the recipient's device.
*   **Confidential:** Even system administrators cannot read the content of your messages.

---

## 🛠️ Technical Overview

For developers and administrators:
*   **Frontend:** Custom HTML5/CSS3 with **Chameleon Theme Engine** for dynamic styling. No heavy frameworks.
*   **Backend:** Pure PHP 8.2 (Vanilla).
*   **Database:** MySQL/MariaDB.
*   **Environment:** XAMPP (Apache + MySQL).

📘 **[View Complete System Architecture & Workflow](SYSTEM_ARCHITECTURE.md)**

### 🌐 Backup Site (Mirror Server)

For high availability, we maintain a secondary mirror server:
*   **URL:** `https://smart-study.azurewebsites.net/`
*   **Purpose:** Ensures access to core study features if the main server is down.
*   **Limitations:**
    *   ❌ **AI Features Disabled:** Gemini/Groq integration is not available on the backup site.
    *   ⚠️ **Messaging:** Real-time chat may experience occasional instability.
    *   🔑 **API Keys:** Do NOT delete your API key if it works on the main server. It may appear as "error" on the backup site simply because AI features are disabled there, not because your key is invalid.

---

## ⚙️ Setup for Developers

1.  **Database:** Import `sql/db.sql` into a database named `capstone_ricardo`.
2.  **Config:** Ensure `php/lib/db.php` points to your MySQL instance.
3.  **Run:** Serve via XAMPP/Apache from the `htdocs` directory.

---

*Developed by the SmartStudy Team | 2026*
