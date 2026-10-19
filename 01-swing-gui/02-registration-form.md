# 2. Registration Form

**Aim:** Collect basic user details in a Swing form.

**Algorithm:** Create frame → add labels and fields → add submit button → show entered details in dialog.

**Pseudocode:** Read name/email → on Submit → display values.

**Flowchart:** Start → Fill form → Click Submit → Display details → Stop.

```java
import javax.swing.*;
import java.awt.*;
public class RegistrationForm {
 public static void main(String[] a) {
  JFrame f=new JFrame("Registration"); f.setLayout(new GridLayout(4,2,5,5));
  JTextField name=new JTextField(), email=new JTextField();
  JComboBox<String> course=new JComboBox<>(new String[]{"CSE","IT","ENTC"});
  f.add(new JLabel("Name")); f.add(name); f.add(new JLabel("Email")); f.add(email);
  f.add(new JLabel("Course")); f.add(course);
  JButton b=new JButton("Submit"); f.add(b);
  b.addActionListener(e->JOptionPane.showMessageDialog(f,name.getText()+"\n"+email.getText()+"\n"+course.getSelectedItem()));
  f.setSize(320,200); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** `JTextField` accepts one-line text; `JComboBox` provides a drop-down; `JOptionPane` displays standard dialogs.