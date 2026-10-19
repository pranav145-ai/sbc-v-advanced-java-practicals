# 5. Student Information Display

**Aim:** Display student details when a button is clicked.

**Algorithm:** Create fields → enter details → click Display → show details.

**Pseudocode:** Read roll, name, marks → display in dialog.

**Flowchart:** Start → Enter student data → Click Display → Show details → Stop.

```java
import javax.swing.*;
import java.awt.*;
public class StudentInfo {
 public static void main(String[] a) {
  JFrame f=new JFrame("Student Info"); f.setLayout(new GridLayout(4,2));
  JTextField roll=new JTextField(), name=new JTextField(), marks=new JTextField();
  f.add(new JLabel("Roll")); f.add(roll); f.add(new JLabel("Name")); f.add(name);
  f.add(new JLabel("Marks")); f.add(marks); JButton b=new JButton("Display"); f.add(b);
  b.addActionListener(e->JOptionPane.showMessageDialog(f,"Roll: "+roll.getText()+"\nName: "+name.getText()+"\nMarks: "+marks.getText()));
  f.setSize(300,200); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** A GUI form collects input using components. `getText()` returns the current text in a text field.