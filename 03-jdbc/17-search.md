# 17. Search Student by ID or Name using JDBC

**Aim:** Retrieve a student by ID or name.

**Algorithm:** Connect → ask search field/value → prepare SELECT → bind value → display result or Not found.

**Pseudocode:** Choose ID/name → execute parameterized SELECT → print matching rows.

**Flowchart:** Start → Choose search field → Enter value → Query DB → Display matches/not found → Stop.

```java
import java.sql.*;
import java.util.*;
public class SearchStudent {
 public static void main(String[] a)throws Exception {
  Scanner in=new Scanner(System.in);
  System.out.print("Search by id or name: ");String field=in.nextLine().trim();
  if(!field.equals("id")&&!field.equals("name")){System.out.println("Choose id or name");return;}
  System.out.print("Value: ");String value=in.nextLine();
  Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
  PreparedStatement p=c.prepareStatement("SELECT * FROM students WHERE "+field+"=?");
  if(field.equals("id"))p.setInt(1,Integer.parseInt(value));else p.setString(1,value);
  ResultSet r=p.executeQuery();
  while(r.next())System.out.println(r.getInt("id")+" "+r.getString("name")+" "+r.getInt("marks"));
  c.close();
 }
}
```

**Viva:** SELECT uses executeQuery; ResultSet.next() moves to the next row. The field name is allow-listed to id/name, while the value is bound using PreparedStatement. Change demo DB credentials to your lab values.