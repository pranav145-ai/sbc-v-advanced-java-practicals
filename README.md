# SBC V — Advanced Java Programming Practicals

Shortest exam-focused examples for all 30 practicals. Each practical aims to include code, algorithm, pseudocode, a text flowchart, output/run notes, and short viva answers.

## Practical index

### 1. Swing GUI
1. [Calculator](01-swing-gui/01-calculator.md)
2. [Registration form](01-swing-gui/02-registration-form.md)
3. [Layout managers](01-swing-gui/03-layout-managers.md)
4. [Temperature converter](01-swing-gui/04-temperature-converter.md)
5. [Student information display](01-swing-gui/05-student-info.md)
6. [Menu-driven text editor](01-swing-gui/06-menu-editor.md)

### 2. AWT/Swing event handling
7. [Login form](02-event-handling/07-login-form.md)
8. [MouseListener](02-event-handling/08-mouse-listener.md)
9. [KeyListener](02-event-handling/09-key-listener.md)
10. [MouseAdapter](02-event-handling/10-mouse-adapter.md)
11. [Arithmetic: inner classes](02-event-handling/11-arithmetic-inner-classes.md)
12. [JColorChooser](02-event-handling/12-color-chooser.md)

### 3. JDBC
13. [Connect and display records](03-jdbc/13-connect-display.md)
14. [Insert using PreparedStatement](03-jdbc/14-insert.md)
15. [Update record](03-jdbc/15-update.md)
16. [Delete record](03-jdbc/16-delete.md)
17. [Search record](03-jdbc/17-search.md)
18. [SQL joins](03-jdbc/18-joins.md)
19. [Display records in JTable](03-jdbc/19-jtable.md)
20. [Transaction commit/rollback](03-jdbc/20-transactions.md)

### 4. Servlets
21. [Hello World with doGet](04-servlets/21-hello-servlet.md)
22. [Process HTML form](04-servlets/22-form-processing.md)
23. [doGet vs doPost](04-servlets/23-get-post.md)
24. [Login servlet](04-servlets/24-login.md)
25. [Sum servlet](04-servlets/25-sum.md)

### 5. JSP and database
26. [JSP welcome/scriptlets](05-jsp/26-welcome.md)
27. [Display students](05-jsp/27-display-students.md)
28. [JSP login with servlet](05-jsp/28-jsp-servlet-login.md)
29. [Insert/display records](05-jsp/29-insert-display.md)
30. [Search/update/delete](05-jsp/30-crud.md)

## Setup notes
- Swing/AWT: JDK 8+; save the public class as the matching `.java` filename, then run `javac FileName.java` and `java FileName`.
- JDBC examples use MySQL Connector/J and a sample database named `college`. Adjust database name, username, password, table/column names to your lab setup. Never commit real passwords.
- Servlet/JSP examples target **Tomcat 9 (`javax.servlet`)**. Tomcat 10+ uses `jakarta.servlet`; change imports accordingly if your lab uses it.
- JDBC driver dependency: MySQL Connector/J must be on the classpath or added to your IDE project.
- Web examples assume a table `students(id INT PRIMARY KEY, name VARCHAR(50), marks INT)`; login examples are teaching demos only, not secure production authentication.

## How to prepare
For each slip, memorise: **purpose → 4–6 algorithm steps → key API/class → output → 2 viva answers**. The flowcharts use a compact text form: Start → Input → Process → Output → Stop.
