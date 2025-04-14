QUE 1
import java.io.*;
import jakarta.servlet.annotation.*;
import jakarta.servlet.http.*;

@WebServlet("/login")
public class LoginServlet extends HttpServlet {
  protected void doPost(HttpServletRequest req, HttpServletResponse res) throws IOException {
    String u = req.getParameter("username"), p = req.getParameter("password");
    res.setContentType("text/html");
    PrintWriter out = res.getWriter();
    out.println("<html><body>");
    if ("admin".equals(u) && "1234".equals(p))
      out.println("<h2>Welcome, " + u + "!</h2>");
    else
      out.println("<h2>Login Failed</h2>");
    out.println("</body></html>");
  }

  protected void doGet(HttpServletRequest req, HttpServletResponse res) throws IOException {
    res.setContentType("text/html");
    PrintWriter out = res.getWriter();
    out.println("<html><body><form method='post' action='login'>"
        + "Username: <input name='username'><br>"
        + "Password: <input type='password' name='password'><br>"
        + "<input type='submit' value='Login'>"
        + "</form></body></html>");
  }
}

QUE 2
import java.io.*; import javax.servlet.*; import javax.servlet.http.*; import javax.servlet.annotation.WebServlet;

@WebServlet("/LoginServlet")
public class LoginServlet extends HttpServlet {
  protected void doGet(HttpServletRequest r, HttpServletResponse s) throws IOException {
    s.setContentType("text/html");
    s.getWriter().println("<form method='post'>" +
      "Username: <input name='user'><br>" +
      "Password: <input name='pass' type='password'><br>" +
      "<input type='submit' value='Login'></form>");
  }

  protected void doPost(HttpServletRequest r, HttpServletResponse s) throws IOException {
    String u = r.getParameter("user"), p = r.getParameter("pass");
    s.setContentType("text/html");
    PrintWriter out = s.getWriter();
    if("admin".equals(u) && "1234".equals(p)) out.println("Welcome " + u + "!");
    else out.println("Login failed. <a href='LoginServlet'>Try again</a>");
  }
}

