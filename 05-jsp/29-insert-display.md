# 29. JSP Insert Student Details and Display Records

**Aim:** Insert a student into MySQL using a JSP form and display the records.

**Algorithm:** Submit ID/name/marks → parameterized INSERT → query all rows → display table.

**Pseudocode:** If form submitted, insert values using PreparedStatement; then SELECT all students and render them.

**Flowchart:** Start → Fill form → Insert row → Fetch records → Display table → Stop.

**students.jsp** (table: students_info(id, name, marks); configure MySQL driver and demo credentials)
```jsp
<%@ page import="java.sql.*" %>
<form method="post">
 ID <input name="id" type="number" required>
 Name <input name="name" required>
 Marks <input name="marks" type="number" required>
 <button type="submit">Insert</button>
</form>
<%
String id=request.getParameter("id"), name=request.getParameter("name"), marks=request.getParameter("marks");
try(Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password")) {
 if(id!=null && name!=null && marks!=null) {
  try(PreparedStatement p=c.prepareStatement("INSERT INTO students_info VALUES(?,?,?)")) {
   p.setInt(1,Integer.parseInt(id));p.setString(2,name);p.setInt(3,Integer.parseInt(marks));p.executeUpdate();
   out.println("Inserted successfully");
  } catch(Exception ex){out.println("Insert failed; check duplicate ID or input");}
 }
 try(Statement s=c.createStatement();ResultSet r=s.executeQuery("SELECT * FROM students_info")) {
  out.println("<table border='1'><tr><th>ID</th><th>Name</th><th>Marks</th></tr>");
  while(r.next())out.println("<tr><td>"+r.getInt(1)+"</td><td>"+r.getString(2)+"</td><td>"+r.getInt(3)+"</td></tr>");
  out.println("</table>");
 }
} catch(Exception e){out.println("Database error; check connection and table");}
%>
```

**Viva:** PreparedStatement binds data separately from SQL. The primary key prevents duplicate IDs. This is an exam-oriented JSP scriptlet example; MVC separates database code from presentation.