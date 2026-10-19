# 23. doGet and doPost

**Aim:** Demonstrate HTTP GET and POST handling.

**Algorithm:** Extend HttpServlet → override both methods → return different responses.

**Pseudocode:** GET request → GET response; POST request → POST response.

**Flowchart:** Start → HTTP request → GET or POST? → Corresponding method → Response → Stop.

```java
import java.io.*;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.*;
@WebServlet("/method")
public class MethodServlet extends HttpServlet {
 protected void doGet(HttpServletRequest q,HttpServletResponse p)throws IOException {p.getWriter().println("Handled GET");}
 protected void doPost(HttpServletRequest q,HttpServletResponse p)throws IOException {p.getWriter().println("Handled POST");}
}
```

**Viva:** GET is commonly used to retrieve resources and parameters may appear in the URL. POST submits data in the request body. Neither method alone provides authentication or encryption; HTTPS provides transport encryption.