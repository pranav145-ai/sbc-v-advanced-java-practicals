# 27. Display students_info Using JSP and JDBC

**Aim:** Create/use the MySQL table students_info and display all records.

**Table setup**
```sql
CREATE TABLE students_info (
 id INT PRIMARY KEY,
 name VARCHAR(50),
 marks INT
);
```

**Algorithm:** Connect to DB → SELECT all rows → loop through ResultSet → render HTML table.

**Pseudocode:** For each students_info row, display ID, name and marks.

**Flowchart:** Start → Connect → SELECT students_info → Loop rows → Display table → Stop.

**students.jsp** (add MySQL Connector/J; change demo credentials)
```jsp
<%@ page import="java.sql.*" %>
<table border="1"><tr><th>ID</th><th>Name</th><th>Marks</th></tr>
<%
try(Connection c=DriverManager.getConnection("jdbc:mysql://localhost:3306/college","root","password");
    Statement s=c.createStatement();
    ResultSet r=s.executeQuery("SELECT id,name,marks FROM students_info")) {
 while(r.next()) {
%>
<tr><td><%=r.getInt("id")%></td><td><%=r.getString("name")%></td><td><%=r.getInt("marks")%></td></tr>
<% } } catch(Exception e) { out.print("Database error: check connection/table"); } %>
</table>
```

**Viva:** JSP can render dynamic HTML; JDBC connects Java to MySQL. ResultSet.next() iterates through records. For larger projects, move database logic into a servlet/DAO rather than scriptlets.