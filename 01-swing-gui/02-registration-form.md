# 2. Student Registration Form

**Aim:** Demonstrate JTextField, JRadioButton, JComboBox, JCheckBox and ButtonGroup.

**Algorithm:** Create fields → group gender radio buttons → add course and hobbies → submit and display values.

**Pseudocode:** Read form controls → build details string → show dialog.

**Flowchart:** Start → Fill form → Submit → Display selected details → Stop.

```java
import javax.swing.*;
import java.awt.*;
public class RegistrationForm {
 public static void main(String[] a) {
  JFrame f=new JFrame("Registration"); f.setLayout(new GridLayout(6,2));
  JTextField name=new JTextField();
  JRadioButton m=new JRadioButton("Male"), w=new JRadioButton("Female");
  ButtonGroup g=new ButtonGroup(); g.add(m); g.add(w);
  JComboBox<String> course=new JComboBox<>(new String[]{"CSE","IT","ENTC"});
  JCheckBox java=new JCheckBox("Java"), sports=new JCheckBox("Sports");
  JButton b=new JButton("Submit");
  f.add(new JLabel("Name"));f.add(name);f.add(new JLabel("Gender"));
  JPanel gp=new JPanel();gp.add(m);gp.add(w);f.add(gp);
  f.add(new JLabel("Course"));f.add(course);f.add(java);f.add(sports);f.add(b);
  b.addActionListener(e->JOptionPane.showMessageDialog(f,"Name: "+name.getText()+"\nGender: "+(m.isSelected()?"Male":w.isSelected()?"Female":"Not selected")+"\nCourse: "+course.getSelectedItem()+"\nJava: "+java.isSelected()+"\nSports: "+sports.isSelected()));
  f.setSize(380,250);f.setDefaultCloseOperation(3);f.setVisible(true);
 }
}
```

**Viva:** ButtonGroup makes radio buttons mutually exclusive. JCheckBox allows multiple choices. JComboBox provides a drop-down. JTextField accepts one-line text.