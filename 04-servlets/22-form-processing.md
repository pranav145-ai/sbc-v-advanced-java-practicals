# 22. Accept Student Details Using HTML Form and Servlet

**Aim:** Collect a student's roll number, name and marks and process them in a servlet.

**Algorithm:** Fill HTML form → submit POST → read parameters → display submitted details.

**Pseudocode:** Read roll/name/marks → write details to response.

**Flowchart:** Start → Fill student form → Submit → Servlet reads values → Display details → Stop.

**student.html**
```html
<form action="student" method="post">
 Roll No: <input name="roll"><br>
 Name: <input name="name"><br>
 Marks: <input name="marks"><br>
 <button type="submit">Submit</button>
</form>
```

**StudentServlet.java** (Tomcat 9; for Tomcat 10+, change javax to jakarta)
```java
import java.io.*;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.*;
@WebServlet("/student")
public class StudentServlet extends HttpServlet {
 protected void doPost(HttpServletRequest q,HttpServletResponse p)throws IOException {
  p.setContentType("text/html;charset=UTF-8");
  p.getWriter().println("<h3>Student Details</h3>Roll: "+q.getParameter("roll")
   +"<br>Name: "+q.getParameter("name")+"<br>Marks: "+q.getParameter("marks"));
 }
}
```

**Viva:** getParameter() retrieves submitted form values. POST data is sent in the request body. Real applications should validate and HTML-escape user input.