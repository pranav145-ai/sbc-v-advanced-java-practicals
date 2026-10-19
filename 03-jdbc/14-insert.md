# 14. JDBC Insert with PreparedStatement

**Aim:** Insert a student row safely using parameters.

**Algorithm:** Connect → prepare INSERT → set parameters → executeUpdate → close.

**Pseudocode:** Set id, name, marks → execute INSERT → print affected rows.

**Flowchart:** Start → Connect → Prepare INSERT → Bind values → Execute → Stop.

```java
import java.sql.*;
public class InsertStudent {
 public static void main(String[] a) throws Exception {
  Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
  PreparedStatement p=c.prepareStatement("INSERT INTO students(id,name,marks) VALUES(?,?,?)");
  p.setInt(1,1); p.setString(2,"Asha"); p.setInt(3,85);
  System.out.println(p.executeUpdate()+" row inserted"); c.close();
 }
}
```

**Viva:** `PreparedStatement` supports parameterized SQL, reduces SQL injection risk, and can be reused. `executeUpdate()` returns affected row count.