# 7. Login Form

**Aim:** Validate a demo username and password.

**Algorithm:** Read credentials → compare with demo values → show success/failure.

**Pseudocode:** If username=admin and password=1234, show success; otherwise failure.

**Flowchart:** Start → Enter credentials → Validate → Success/Failure → Stop.

```java
import javax.swing.*;
import java.awt.*;
public class LoginForm {
 public static void main(String[] a) {
  JFrame f=new JFrame("Login"); f.setLayout(new GridLayout(3,2));
  JTextField u=new JTextField(); JPasswordField p=new JPasswordField();
  f.add(new JLabel("Username")); f.add(u); f.add(new JLabel("Password")); f.add(p);
  JButton b=new JButton("Login"); f.add(b);
  b.addActionListener(e->JOptionPane.showMessageDialog(f,u.getText().equals("admin")&&new String(p.getPassword()).equals("1234")?"Login successful":"Invalid login"));
  f.setSize(280,150); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** `JPasswordField` masks typed characters. This hard-coded check is for lab demonstration only, not production security.