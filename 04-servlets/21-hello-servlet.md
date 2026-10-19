# 21. Hello World Servlet (doGet)

**Aim:** Send a simple response from a servlet.

**Algorithm:** Map servlet URL → handle GET request → set content type → write response.

**Pseudocode:** On GET → response writer prints greeting.

**Flowchart:** Start → Browser sends GET → Servlet runs → HTML response → Stop.

```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;
import javax.servlet.annotation.WebServlet;
@WebServlet("/hello")
public class HelloServlet extends HttpServlet {
 protected void doGet(HttpServletRequest req,HttpServletResponse res)throws IOException {
  res.setContentType("text/html"); res.getWriter().println("<h2>Hello World</h2>");
 }
}
```

**Run:** Deploy to Tomcat 9; visit `http://localhost:8080/YourApp/hello`. Tomcat 10+ uses `jakarta.servlet.*`.

**Viva:** Servlet is a server-side Java component. doGet handles HTTP GET; HttpServletRequest represents request data and HttpServletResponse builds the response.