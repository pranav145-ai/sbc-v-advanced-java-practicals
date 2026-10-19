# 26. JSP Welcome Page and Scriptlet

**Aim:** Display a greeting using JSP.

**Algorithm:** Open JSP page → execute scriptlet → print greeting.

**Pseudocode:** Get name → output welcome message.

**Flowchart:** Start → Browser requests JSP → Server executes JSP → HTML response → Stop.

```jsp
<%@ page contentType="text/html;charset=UTF-8" %>
<html><body>
<%
 String name=request.getParameter("name");
 if(name==null) name="Student";
%>
<h2>Welcome, <%= name %>!</h2>
</body></html>
```

**Viva:** JSP creates dynamic web pages. A scriptlet uses `<% ... %>`; an expression `<%= ... %>` prints a value. Modern projects prefer EL/JSTL over scriptlets.