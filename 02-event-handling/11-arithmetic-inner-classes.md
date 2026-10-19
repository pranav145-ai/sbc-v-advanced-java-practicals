# 11. Arithmetic Using Named and Anonymous Inner Classes

**Aim:** Perform arithmetic using named and anonymous event handlers. This compact example uses addition and demonstrates both styles.

**Algorithm:** Create two fields and buttons → named inner class handles Add → anonymous class handles Subtract → show results.

**Pseudocode:** On Add, display a+b; on Subtract, display a-b.

**Flowchart:** Start → Enter two numbers → Choose operation → Calculate → Display result → Stop.

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
public class ArithmeticInner extends JFrame {
 JTextField a=new JTextField(5),b=new JTextField(5),r=new JTextField(7);
 ArithmeticInner(){
  JButton add=new JButton("Add"),sub=new JButton("Subtract");
  add.addActionListener(new AddHandler());
  sub.addActionListener(new ActionListener(){public void actionPerformed(ActionEvent e){calc(false);}});
  setLayout(new FlowLayout());add(a);add(b);add(add);add(sub);add(r);
  setSize(320,130);setDefaultCloseOperation(3);setVisible(true);
 }
 void calc(boolean plus){try{double x=Double.parseDouble(a.getText()),y=Double.parseDouble(b.getText());r.setText(""+(plus?x+y:x-y));}catch(Exception e){r.setText("Invalid");}}
 class AddHandler implements ActionListener {public void actionPerformed(ActionEvent e){calc(true);}}
 public static void main(String[] x){new ArithmeticInner();}
}
```

**Viva:** A named inner class has a declared class name. An anonymous inner class is declared and instantiated in one expression. Both can access members of the enclosing object.