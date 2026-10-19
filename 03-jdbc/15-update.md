# 15. JDBC Update

**Aim:** Update marks for a student ID.

**Algorithm:** Connect → prepare UPDATE → set marks and ID → execute → report count.

**Pseudocode:** UPDATE students SET marks=? WHERE id=? → executeUpdate.

**Flowchart:** Start → Connect → Bind update values → Execute UPDATE → Show row count → Stop.

```java
import java.sql.*;
public class UpdateStudent {
 public static void main(String[] a) throws Exception {
  Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
  PreparedStatement p=c.prepareStatement("UPDATE students SET marks=? WHERE id=?");
  p.setInt(1,90); p.setInt(2,1); System.out.println(p.executeUpdate()+" row(s) updated"); c.close();
 }
}
```

**Viva:** UPDATE modifies existing rows. The WHERE clause limits which rows are changed; without it, every row may be updated.