# Campus SkillTrader 🎓💼

Campus SkillTrader is a desktop application built in Java that serves as a cashless, peer-to-peer matchmaking platform for university students. 

The project solves a major campus pain point: **student financial stress**. Instead of spending money they don't have on services (like fixing a crashed laptop), students trade their skills. A student who can fix a computer might trade their time with a student who can offer mathematics tutoring or graphic design. By removing money from the equation, this app reduces financial strain on both students and their parents.


## 🚀 Key Features

* **Cashless Ecosystem:** Designed purely for peer-to-peer student skill exchanges.
* **Smart Matchmaking Engine:** Queries the SQL database to instantly pair students based on "Skill Offered" vs. "Skill Requested."
* **Asynchronous Match Timer (Multithreading):** Utilizes Java Threads to run a 60-second real-time search background worker. If a live match is not found within 1 minute, the app seamlessly saves the user's profile to the pool and updates their status.
* **Modern GUI:** Built with a clean, responsive layout using **JavaFX**.


## 🛠️ Tech Stack

* **Language:** Java (JDK 17+)
* **Framework:** JavaFX (UI/UX)
* **Database:** SQL (JDBC connection for user profiles and matchmaking pools)
* **Concurrency:** Java Threads (Background time-out and search processing)

## ⚙️ How It Works (The Matchmaking Logic)

1. **Registration:** The student enters their Name, Contact Info (Email/Phone), **Skill They Have**, and **Skill They Need**.
2. **The Search:** The app initiates a background "Thread" that polls the database for an exact reciprocal match:
   $$\text{Student A (Has: Java, Wants: PC Repair)} \iff \text{Student B (Has: PC Repair, Wants: Java)}$$
3. **Timeout Rule:** The thread counts down for 60 seconds. 
   * **If matched:** The app immediately displays the contact details of both students on screen.
   * **If no match:** The application saves the student's entry into the database pool so they can be matched passively when another student signs up.

---

## 💻 Future Enhancements

* Move from a desktop app to a central web/mobile API.
* Add an in-app messaging system to secure student contact privacy.
* Implement a rating/review system to ensure skill quality and safety on campus.
