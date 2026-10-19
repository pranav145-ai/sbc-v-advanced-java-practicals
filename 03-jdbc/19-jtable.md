# 19. Display JDBC Records in JTable

**Aim:** Display database records in a Swing table.

**Algorithm:** Connect → query records → add rows to DefaultTableModel → show model in JTable.

**Pseudocode:** Create columns → query → append each row → display table.

**Flowchart:** Start → Connect → Fetch rows → Fill table model → Display JTable → Stop.

```java
import javax.swing.*;
import javax.swing.table.*;
import java.sql.*;
public class StudentTable {
 public static void main(String[] a) throws Exception {
  Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
  ResultSet r=c.createStatement().executeQuery("SELECT id,name,marks FROM students");
  DefaultTableModel m=new DefaultTableModel(new String[]{"ID","Name","Marks"},0);
  while(r.next()) m.addRow(new Object[]{r.getInt(1),r.getString(2),r.getInt(3)});
  JFrame f=new JFrame("Students"); f.add(new JScrollPane(new JTable(m)));
  f.setSize(400,250); f.setDefaultCloseOperation(3); f.setVisible(true); c.close();
 }
}
```

**Viva:** JTable displays tabular data. DefaultTableModel stores editable rows and columns; JScrollPane adds scrolling.