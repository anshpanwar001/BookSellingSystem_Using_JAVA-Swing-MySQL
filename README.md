<div align="center">

# 📚 Book Hub
### Buy · Sell · Recycle

A Java Swing desktop application for trading new and second-hand textbooks, with separate **Admin** and **User** portals.

![Java](https://img.shields.io/badge/Java-8%2B-orange?logo=openjdk&logoColor=white)
![Swing](https://img.shields.io/badge/GUI-Swing%20%2F%20AWT-blue)
![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?logo=mysql&logoColor=white)
![Status](https://img.shields.io/badge/status-in%20development-yellow)

</div>

---

## ✨ Overview

**Book Hub** is a textbook marketplace built with Java Swing. Students can browse and buy books, or recycle their old ones. Admins can list new and old stock and view orders. The app aims to make textbooks cheaper and more reusable.

## 🚀 Features

### 👤 User Portal
- Create an account (stored in MySQL via JDBC)
- Login screen
- Buy books and enter a delivery address
- Order confirmation with a randomly generated **Order ID**
- Recycle (sell) your old books
- Raise a support request and receive a **Request ID**
- Order history and contact screens (UI in place)

### 🛠️ Admin Portal
- Secure admin login
- Add **new** books and **old** books (title, author, publisher, subject, price, source, published date)
- View bookings / orders
- Management screens for users, admins and orders (UI in place)

## 🧰 Tech Stack

| Layer      | Technology                       |
|------------|----------------------------------|
| Language   | Java                             |
| GUI        | Swing, AWT                       |
| Database   | MySQL (JDBC, `mysql-connector-j`)|
| Packaging  | Executable JAR (`Book_Hub.jar`)  |

## 📁 Project Structure

```
Textbook_selling_system/
├── Book_selling_system.java   # Entry point
├── Main_screen.java           # Landing screen (Admin / User)
├── AdminLogin.java            # Admin authentication
├── AdminHost.java             # Admin dashboard
├── Userlogin.java             # User authentication
├── UserHost.java              # User dashboard
├── Create_ac.java             # User registration (MySQL)
├── BuyBooks.java              # Browse / buy books
├── Address.java               # Delivery address & order placement
├── Add_new_books.java         # Admin: add new books
├── Add_old_books.java         # Add old / recycled books
├── Show_bookings.java         # Admin: view orders
└── Request.java               # Support request form
```

## ⚙️ Getting Started

### Prerequisites
- JDK 8 or higher
- MySQL Server
- [MySQL Connector/J](https://dev.mysql.com/downloads/connector/j/) on your classpath

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

### 2. Set up the database
```sql
CREATE DATABASE `book selling system`;
USE `book selling system`;

CREATE TABLE account (
  first_name VARCHAR(50),
  last_name  VARCHAR(50),
  username   VARCHAR(50) PRIMARY KEY,
  password   VARCHAR(100),
  email      VARCHAR(100),
  mobile     VARCHAR(10)
);
```
The default connection is `jdbc:mysql://localhost:3306/book selling system` with user `root` and an empty password. Change it in `Create_ac.java` to match your setup.

### 3. Run the app
**Option A: run the JAR**
```bash
java -jar Book_Hub.jar
```

**Option B: compile and run**
```bash
javac -cp ".:mysql-connector-j.jar" Textbook_selling_system/*.java
java  -cp ".:mysql-connector-j.jar" Textbook_selling_system.Book_selling_system
```
(Use `;` instead of `:` on Windows.)

> **Note:** Background and icon images are loaded from absolute Windows paths. If images don't appear, update those paths or move the images into a `resources/` folder.

## 🗺️ Roadmap

- [ ] Replace hardcoded admin credentials with database-backed login
- [ ] Finish user login against the `account` table
- [ ] Hash passwords (BCrypt) instead of storing plain text
- [ ] Use `PreparedStatement` to prevent SQL injection
- [ ] Persist books and orders in MySQL and load them into the Buy Books table
- [ ] Implement Manage Users / Orders / Admins screens
- [ ] Load images from classpath resources instead of absolute paths
- [ ] Replace absolute-positioned layouts with layout managers
- [ ] Add input validation for forms

## 🤝 Contributing

Contributions, issues and feature requests are welcome. Fork the repo, create a branch and open a pull request.

## 👨‍💻 Author

Built by **Ansh Panwar** · [GitHub](https://github.com/anshpanwar001)

## 📄 License

Distributed under the MIT License. See `LICENSE` for details.
