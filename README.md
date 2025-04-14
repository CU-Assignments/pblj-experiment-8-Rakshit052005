[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/RHnMb-7L)

Que 1 HTML CODE

<!DOCTYPE html>
<html>
<body>
  <form action="LoginServlet" method="post">
    Username: <input name="username"><br>
    Password: <input name="password" type="password"><br>
    <input type="submit" value="Login">
  </form>
</body>
</html>


SERVLET CODE

import java.io.*;
import jakarta.servlet.*;
import jakarta.servlet.http.*;

public class LoginServlet extends HttpServlet {
  protected void doPost(HttpServletRequest req, HttpServletResponse res) throws IOException {
    String u = req.getParameter("username"), p = req.getParameter("password");
    PrintWriter out = res.getWriter();
    res.setContentType("text/html");
    if("admin".equals(u) && "1234".equals(p))
      out.print("<h2>Welcome, " + u + "!</h2>");
    else
      out.print("<h2>Login Failed</h2>");
  }
}



QUE 2  HTML CODE

<form action="LoginServlet" method="post">
  Username: <input name="user"><br>
  Password: <input name="pass" type="password"><br>
  <input type="submit" value="Login">
</form>


SERVLET CODE

import java.io.*; import javax.servlet.*; import javax.servlet.http.*;

public class LoginServlet extends HttpServlet {
  protected void doPost(HttpServletRequest r, HttpServletResponse s) throws IOException {
    String u = r.getParameter("user"), p = r.getParameter("pass");
    s.setContentType("text/html");
    PrintWriter out = s.getWriter();
    if("admin".equals(u) && "1234".equals(p)) out.println("Welcome " + u + "!");
    else out.println("Login failed.");
  }
}
