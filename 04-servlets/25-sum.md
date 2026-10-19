# 25. Sum of Two Numbers Servlet

**Aim:** Add two values submitted from an HTML form.

**Algorithm:** Receive a and b → parse integers → add → display result.

**Pseudocode:** sum = Integer.parseInt(a)+Integer.parseInt(b) → output sum.

**Flowchart:** Start → Input a,b → Parse → Add → Display sum → Stop.

**sum.html**
```html
<form action="sum" method="get">
 <input name="a" type="number"><input name="b" type="number"><button>Add</button>
</form>
```

**SumServlet.java**
```java
import java.io.*;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.*;
@WebServlet("/sum")
public class SumServlet extends HttpServlet {
 protected void doGet(HttpServletRequest q,HttpServletResponse p)throws IOException {
  p.setContentType("text/html");
  try {int s=Integer.parseInt(q.getParameter("a"))+Integer.parseInt(q.getParameter("b"));p.getWriter().println("Sum = "+s);}
  catch(Exception e){p.getWriter().println("Enter valid integers");}
 }
}
```

**Viva:** `parseInt()` converts text to an integer. Invalid or missing input can cause an exception, so input is validated using try/catch.