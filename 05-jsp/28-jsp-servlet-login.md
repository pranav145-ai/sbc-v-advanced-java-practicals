# 28. JSP Login with Servlet

**Aim:** Submit credentials from JSP to a servlet.

**Algorithm:** JSP form → servlet reads values → validates demo credentials → responds.

**Pseudocode:** If user/password match demo values, output success else failure.

**Flowchart:** Start → JSP form → Submit POST → Servlet validates → Result → Stop.

**login.jsp**
```jsp
<form action="login" method="post">
 <input name="user" placeholder="Username">
 <input name="pass" type="password" placeholder="Password">
 <button>Login</button>
</form>
```

**LoginServlet.java**
```java
import java.io.*;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.*;
@WebServlet("/login")
public class LoginServlet extends HttpServlet {
 protected void doPost(HttpServletRequest q,HttpServletResponse p)throws IOException {
  p.setContentType("text/html");
  boolean ok="admin".equals(q.getParameter("user"))&&"1234".equals(q.getParameter("pass"));
  p.getWriter().print(ok?"Welcome":"Invalid credentials");
 }
}
```

**Viva:** JSP is used for presentation and servlet for request handling. This example uses demo credentials only; real apps need secure password storage and sessions.