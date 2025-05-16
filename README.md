# Interactive Quiz Game 🧠✨

Welcome to the Interactive Quiz Game! This project is a robust quiz application developed in Java, featuring a graphical user interface built with Java Swing and persistent data storage using MySQL. Players can engage with multiple-choice questions, track their scores, and enjoy a seamless interactive learning experience.

---

## ✨ Features

* **Graphical User Interface (GUI):** A user-friendly and interactive interface designed with **Java Swing** for an enhanced visual experience.
* **Multiple-Choice Questions:** Presents a series of well-structured questions with distinct answer options.
* **Dynamic Scoring System:** Accurately tracks the player's correct and incorrect responses to calculate a final score.
* **Persistent Data Storage:** Questions, answers, and potentially player scores are managed and stored using **MySQL database**, allowing for easy updates and scalability.
* **User Engagement:** Designed to be intuitive, fun, and educational, promoting an enjoyable way to learn.
* **Clear Feedback:** Provides immediate visual feedback on the correctness of each answer.

---

## 🛠️ Technologies Used

* **Core Language:** Java ☕
* **GUI Framework:** Java Swing 🎨
* **Database:** MySQL 🗄️
* **Database Connectivity:** JDBC (Java Database Connectivity)

---

## 🚀 Getting Started

Follow these steps to get a local copy of the project up and running on your machine.

### Prerequisites

Before you begin, ensure you have the following installed:

* **Java Development Kit (JDK) 8 or higher**
* **MySQL Server** and **MySQL Workbench** (or another client)
* **Maven** (if you use Maven for project management, otherwise direct compilation)
* **A text editor or IDE** (e.g., IntelliJ IDEA, Eclipse)
* **Git**
* **MySQL JDBC Connector JAR:** You will need to download the MySQL Connector/J (JDBC driver) JAR file and add it to your project's classpath.

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/amit-soham-16/QuizGame-.git
    cd QuizGame-
    ```

2.  **Database Setup (MySQL):**
    * Log in to your MySQL server (e.g., via MySQL Workbench or command line).
    * Create a new database for the quiz game:
        ```sql
        CREATE DATABASE quiz_game_db;
        USE quiz_game_db;
        ```
    * Create the necessary tables (e.g., `questions`, `options`, `scores`). You'll need to define your table schemas here.
        *Example (adapt to your actual schema):*
        ```sql
        CREATE TABLE questions (
            id INT AUTO_INCREMENT PRIMARY KEY,
            question_text TEXT NOT NULL
        );

        CREATE TABLE options (
            id INT AUTO_INCREMENT PRIMARY KEY,
            question_id INT NOT NULL,
            option_text VARCHAR(255) NOT NULL,
            is_correct BOOLEAN NOT NULL,
            FOREIGN KEY (question_id) REFERENCES questions(id)
        );

        -- You might want a table to store initial questions/answers or load them dynamically
        -- INSERT INTO questions (question_text) VALUES ('What is the capital of France?');
        -- INSERT INTO options (question_id, option_text, is_correct) VALUES (1, 'Paris', TRUE);
        -- INSERT INTO options (question_id, option_text, is_correct) VALUES (1, 'Rome', FALSE);
        ```
    * **Configure Database Connection:** Open your Java project in your IDE. Locate the file where your database connection details are stored (e.g., a `DbConnection.java` file, or properties file). Update the `url`, `username`, and `password` to match your MySQL setup.
        *Example (pseudo-code for connection string):*
        ```java
        // In your DbConnection.java or similar file
        private static final String DB_URL = "jdbc:mysql://localhost:3306/quiz_game_db";
        private static final String DB_USER = "your_mysql_username";
        private static final String DB_PASSWORD = "your_mysql_password";
        ```

3.  **Add MySQL JDBC Connector to Classpath:**
    * Download the MySQL Connector/J JAR from the official MySQL website.
    * Place the JAR file in a `lib` directory within your project, or add it directly to your IDE's project build path.
        * **For IDEs (e.g., IntelliJ IDEA):** Go to `File` -> `Project Structure` -> `Modules` -> `Dependencies` -> `+` -> `JARs or Directories...` and select the downloaded JAR.
        * **For Manual Compilation:** You'll need to include it in the `javac` and `java` commands using `-cp` or `--class-path`.

4.  **Build and Run the application:**
    * **Using IDE (Recommended):** Open the project in your IDE (e.g., IntelliJ IDEA, Eclipse). Let the IDE resolve dependencies. Find your main class (e.g., `QuizApp.java` or `Main.java`) and run it directly.
    * **Using Command Line (More complex with Swing/MySQL JARs):**
        ```bash
        # Compile (adjust paths and include JDBC JAR)
        javac -cp ".;path/to/mysql-connector-j-8.x.x.jar" src/com/yourpackage/QuizGameMain.java # Adjust paths

        # Run (adjust paths and include JDBC JAR)
        java -cp ".;path/to/mysql-connector-j-8.x.x.jar" com.yourpackage.QuizGameMain # Adjust paths
        ```
        *(Replace `path/to/mysql-connector-j-8.x.x.jar` with the actual path to your downloaded JAR. Replace `com.yourpackage.QuizGameMain` with your actual main class including its package structure.)*

---

## 🖥️ How to Play

1.  Ensure your MySQL server is running and the database is configured as per the "Database Setup" steps.
2.  Launch the application.
3.  The GUI will present you with quiz questions.
4.  Select your answer using the provided options (e.g., radio buttons, buttons).
5.  Receive immediate feedback and proceed through the quiz.
6.  Your final score will be displayed at the end!

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

---


## 👨‍💻 Author
- Amit Kumar
- 📫 amitk1602info@gmail.com
- 🔗 [LinkedIn](https://www.linkedin.com/in/kumaramit02/) | [GitHub](https://github.com/amit-soham-16)





## ⭐️ Show Your Support
If you like this project, give it a ⭐️ on GitHub! Contributions and suggestions are always welcome.
