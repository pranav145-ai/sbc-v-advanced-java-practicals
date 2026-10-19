# 29. Insert and Display Records

**Aim:** Insert a student through a form and display records from JSP.

**Algorithm:** Form submits ID/name/marks → server validates → PreparedStatement inserts → query and display records.

**Pseudocode:** Read form values → parameterized INSERT → show status. Display query results separately.

**Flowchart:** Start → Enter data → Validate → Insert row → Show status → Stop.

**insert.html**
```html
<form action="insert" method="post">
 ID <input name="id" type="number">
 Name <input name="name">
 Marks <input name="marks" type="number">
 <button>Insert</button>
</form>
```

**InsertServlet.java**
```java
import java.io.*;
import java.sql.*;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.*;
@WebServlet("/insert")
public class InsertServlet extends HttpServlet {
 protected void doPost(HttpServletRequest q,HttpServletResponse p)throws IOException {
  p.setContentType("text/plain");
  try(Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
      PreparedStatement s=c.prepareStatement("INSERT INTO students VALUES(?,?,?)")) {
   s.setInt(1,Integer.parseInt(q.getParameter("id"))); s.setString(2,q.getParameter("name"));
   s.setInt(3,Integer.parseInt(q.getParameter("marks"))); s.executeUpdate(); p.getWriter().print("Inserted");
  } catch(Exception e){p.getWriter().print("Insert failed; check values/database");}
 }
}
```

**Viva:** PreparedStatement binds values separately from SQL. Keep database access in a servlet/DAO and use JSP to display rows; never commit real passwords.