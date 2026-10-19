# 11. Arithmetic Using Inner Classes

**Aim:** Perform addition using a named inner class as event handler.

**Algorithm:** Create two fields and button → inner listener reads values → displays sum.

**Pseudocode:** On click, parse a,b → show a+b.

**Flowchart:** Start → Enter values → Click Add → Compute sum → Display → Stop.

```java
import javax.swing.*;
public class ArithmeticInner {
 JTextField a=new JTextField(5), b=new JTextField(5);
 ArithmeticInner(){
  JFrame f=new JFrame("Addition"); JButton add=new JButton("Add"); JLabel out=new JLabel("Result");
  f.add(a,"North"); f.add(b,"Center"); f.add(add,"West"); f.add(out,"East");
  add.addActionListener(new Handler(out)); f.setSize(300,120); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
 class Handler implements java.awt.event.ActionListener {
  JLabel out; Handler(JLabel l){out=l;}
  public void actionPerformed(java.awt.event.ActionEvent e){try{out.setText(""+(Double.parseDouble(a.getText())+Double.parseDouble(b.getText())));}catch(Exception ex){out.setText("Invalid");}}
 }
 public static void main(String[] x){new ArithmeticInner();}
}
```

**Viva:** An inner class is declared inside another class. It can access the enclosing object's members.