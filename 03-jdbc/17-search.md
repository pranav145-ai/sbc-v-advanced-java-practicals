# 17. JDBC Search

**Aim:** Find a student by ID.

**Algorithm:** Connect → prepare SELECT with ID → bind ID → read result → display or not found.

**Pseudocode:** SELECT * WHERE id=? → if next row, print it; else print not found.

**Flowchart:** Start → Input ID → Query DB → Found? → Display/Not found → Stop.

```java
import java.sql.*;
public class SearchStudent {
 public static void main(String[] a) throws Exception {
  Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
  PreparedStatement p=c.prepareStatement("SELECT * FROM students WHERE id=?"); p.setInt(1,1);
  ResultSet r=p.executeQuery();
  if(r.next()) System.out.println(r.getInt("id")+" "+r.getString("name")+" "+r.getInt("marks"));
  else System.out.println("Not found");
  c.close();
 }
}
```

**Viva:** `executeQuery()` is used for SELECT and returns a ResultSet. `next()` advances to the next row.