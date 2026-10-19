# 30. JSP Student Management: Search, Update and Delete

**Aim:** Search, update and delete records using JDBC from JSP.

**Table:** `students_info(id INT PRIMARY KEY, name VARCHAR(50), marks INT)`.

**Algorithm:** Select operation → read ID/value → execute parameterized SQL → show result.

**Pseudocode:** Search: SELECT by ID. Update: set name/marks by ID. Delete: remove row by ID.

**Flowchart:** Start → Choose operation → Enter ID/details → Execute SQL → Show result → Stop.

**student-crud.jsp** (exam demo; configure MySQL Connector/J and credentials)
```jsp
<%@ page import="java.sql.*" %>
<form method="post">
 ID <input name="id" type="number" required>
 Name (for update) <input name="name">
 Marks (for update) <input name="marks" type="number">
 <button name="op" value="search">Search</button>
 <button name="op" value="update">Update</button>
 <button name="op" value="delete">Delete</button>
</form>
<%
String id=request.getParameter("id"), op=request.getParameter("op");
if(id!=null && op!=null) {
 try(Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password")) {
  if(op.equals("search")) {
   try(PreparedStatement p=c.prepareStatement("SELECT * FROM students_info WHERE id=?")) {
    p.setInt(1,Integer.parseInt(id));try(ResultSet r=p.executeQuery()) {
     if(r.next())out.println("ID: "+r.getInt(1)+" Name: "+r.getString(2)+" Marks: "+r.getInt(3));
     else out.println("Not found");
    }
   }
  } else if(op.equals("update")) {
   try(PreparedStatement p=c.prepareStatement("UPDATE students_info SET name=?,marks=? WHERE id=?")) {
    p.setString(1,request.getParameter("name"));p.setInt(2,Integer.parseInt(request.getParameter("marks")));p.setInt(3,Integer.parseInt(id));
    out.println(p.executeUpdate()+" row(s) updated");
   }
  } else if(op.equals("delete")) {
   try(PreparedStatement p=c.prepareStatement("DELETE FROM students_info WHERE id=?")) {
    p.setInt(1,Integer.parseInt(id));out.println(p.executeUpdate()+" row(s) deleted");
   }
  }
 } catch(Exception e){out.println("Operation failed; check inputs/database");}
}
%>
```

**Viva:** CRUD = Create, Read, Update, Delete. SELECT uses executeQuery; UPDATE/DELETE use executeUpdate. Always use PreparedStatement and validate inputs. This is a compact teaching demo, not production-secure output handling.