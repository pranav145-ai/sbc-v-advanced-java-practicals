# 22. Process HTML Form with Servlet

**Aim:** Read a submitted form field.

**Algorithm:** Create form → submit to servlet → read parameter → respond.

**Pseudocode:** name = request.getParameter("name") → print greeting.

**Flowchart:** Start → Fill form → Submit → Read parameter → Display response → Stop.

**form.html**
```html
<form action="greet" method="post">
 Name: <input name="name"><button>Send</button>
</form>
```

**GreetServlet.java**
```java
import java.io.*;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.*;
@WebServlet("/greet")
public class GreetServlet extends HttpServlet {
 protected void doPost(HttpServletRequest q,HttpServletResponse p)throws IOException {
  p.setContentType("text/html");
  p.getWriter().println("Hello, "+q.getParameter("name"));
 }
}
```

**Viva:** `getParameter()` reads a submitted parameter. POST sends form data in the request body; validate and escape user input in real applications.