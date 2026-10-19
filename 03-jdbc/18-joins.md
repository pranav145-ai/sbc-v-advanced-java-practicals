# 18. SQL Joins via JDBC

**Aim:** Display students with their department names.

**Prerequisite:** Example tables `students(id,name,dept_id)` and `departments(id,dept_name)`.

**Algorithm:** Connect → execute JOIN query → print joined columns.

**Pseudocode:** Select student name and department name using matching department IDs.

**Flowchart:** Start → Connect → Execute JOIN → Print results → Close → Stop.

```java
import java.sql.*;
public class JoinDemo {
 public static void main(String[] a) throws Exception {
  Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
  ResultSet r=c.createStatement().executeQuery("SELECT s.name,d.dept_name FROM students s JOIN departments d ON s.dept_id=d.id");
  while(r.next()) System.out.println(r.getString(1)+" - "+r.getString(2));
  c.close();
 }
}
```

**Viva:** INNER JOIN returns matching rows. LEFT JOIN returns all left-table rows and matching right-table data (or NULL). ON defines the match condition.