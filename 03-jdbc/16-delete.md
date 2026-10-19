# 16. JDBC Delete

**Aim:** Delete a student by ID.

**Algorithm:** Connect → prepare DELETE → set ID → executeUpdate → close.

**Pseudocode:** DELETE FROM students WHERE id=? → bind ID → execute.

**Flowchart:** Start → Connect → Enter ID → Execute DELETE → Show affected rows → Stop.

```java
import java.sql.*;
public class DeleteStudent {
 public static void main(String[] a) throws Exception {
  Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
  PreparedStatement p=c.prepareStatement("DELETE FROM students WHERE id=?");
  p.setInt(1,1); System.out.println(p.executeUpdate()+" row(s) deleted"); c.close();
 }
}
```

**Viva:** DELETE removes rows. WHERE identifies the target row; always verify the condition before executing a delete.