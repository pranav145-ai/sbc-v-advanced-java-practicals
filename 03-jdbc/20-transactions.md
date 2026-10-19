# 20. JDBC Transactions: Commit and Rollback

**Aim:** Demonstrate transaction control.

**Algorithm:** Connect → disable auto-commit → run SQL → commit on success → rollback on failure.

**Pseudocode:** setAutoCommit(false) → execute operation → commit; on exception rollback.

**Flowchart:** Start → Begin transaction → Execute SQL → Success? → Commit / Rollback → Stop.

```java
import java.sql.*;
public class TransactionDemo {
 public static void main(String[] a) throws Exception {
  Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
  try {
   c.setAutoCommit(false);
   PreparedStatement p=c.prepareStatement("UPDATE students SET marks=marks+1 WHERE id=?");
   p.setInt(1,1); p.executeUpdate(); c.commit(); System.out.println("Committed");
  } catch(Exception e) { c.rollback(); System.out.println("Rolled back"); }
  finally { c.close(); }
 }
}
```

**Viva:** A transaction is a logical unit of work. COMMIT saves changes; ROLLBACK cancels uncommitted changes; ACID means Atomicity, Consistency, Isolation, Durability.