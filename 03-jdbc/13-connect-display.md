# 13. JDBC: Connect and Display

**Aim:** Connect Java to MySQL and display student rows.

**Algorithm:** Load driver → connect → execute SELECT → print rows → close connection.

**Pseudocode:** Connect → query students → while rows exist print id/name/marks → close.

**Flowchart:** Start → Connect DB → Execute SELECT → Display rows → Close → Stop.

```java
import java.sql.*;
public class ConnectDisplay {
 public static void main(String[] a) throws Exception {
  Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
  ResultSet r=c.createStatement().executeQuery("SELECT * FROM students");
  while(r.next()) System.out.println(r.getInt("id")+" "+r.getString("name")+" "+r.getInt("marks"));
  c.close();
 }
}
```

**Viva:** JDBC connects Java to databases. `Connection` represents a DB session; `Statement` executes SQL; `ResultSet` stores query rows. Replace demo credentials with your local lab credentials.