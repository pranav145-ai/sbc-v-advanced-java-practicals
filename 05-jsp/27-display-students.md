# 27. Display Students in JSP

**Aim:** Read student records from MySQL and display them in HTML.

**Algorithm:** Connect DB → query students → loop over rows → print table.

**Pseudocode:** For each row, output id, name, marks.

**Flowchart:** Start → Connect → SELECT → Loop rows → Render table → Close → Stop.

```jsp
<%@ page import="java.sql.*" %>
<table border="1"><tr><th>ID</th><th>Name</th><th>Marks</th></tr>
<%
try(Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
    Statement s=c.createStatement();
    ResultSet r=s.executeQuery("SELECT id,name,marks FROM students")) {
 while(r.next()) {
%>
<tr><td><%=r.getInt(1)%></td><td><%=r.getString(2)%></td><td><%=r.getInt(3)%></td></tr>
<% } } catch(Exception e) { out.print("Database error"); } %>
</table>
```

**Viva:** JSP can embed Java, but scriptlet-heavy database pages mix presentation and logic. A servlet/DAO with JSP rendering is better practice. Configure the MySQL driver and replace demo credentials.