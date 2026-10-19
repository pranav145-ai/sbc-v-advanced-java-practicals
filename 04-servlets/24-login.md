# 24. Login Servlet

**Aim:** Check demo credentials submitted by a form.

**Algorithm:** Read username/password → compare demo values → show result.

**Pseudocode:** If admin/1234, print success; else print invalid.

**Flowchart:** Start → Submit credentials → Validate → Success/Failure → Stop.

**login.html**
```html
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
  p.getWriter().println(ok?"Login successful":"Invalid login");
 }
}
```

**Viva:** `doPost()` processes form submissions. This hard-coded credential check is only for practice; production apps need hashed passwords, sessions, and validation.