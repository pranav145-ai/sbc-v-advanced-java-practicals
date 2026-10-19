# 1. Simple Swing Calculator

**Aim:** Perform two-number arithmetic using Swing.

**Algorithm:** 1. Create frame and two text fields. 2. Add operation buttons. 3. Read numbers on click. 4. Calculate and show result.

**Pseudocode:** Input a,b → choose operation → calculate → display result.

**Flowchart:** Start → Enter two numbers → Select +/−/×/÷ → Calculate → Show result → Stop.

```java
import javax.swing.*;
import java.awt.*;
public class Calculator {
 public static void main(String[] x) {
  JFrame f=new JFrame("Calculator"); f.setLayout(new GridLayout(4,2));
  JTextField a=new JTextField(), b=new JTextField(), r=new JTextField(); r.setEditable(false);
  f.add(new JLabel("First")); f.add(a); f.add(new JLabel("Second")); f.add(b);
  for(String op:new String[]{"+","-","*","/"}) {
   JButton btn=new JButton(op); f.add(btn);
   btn.addActionListener(e->{try{double n=Double.parseDouble(a.getText()),m=Double.parseDouble(b.getText()); r.setText(""+(op.equals("+")?n+m:op.equals("-")?n-m:op.equals("*")?n*m:n/m));}catch(Exception ex){r.setText("Invalid input");}});
  }
  f.add(new JLabel("Result")); f.add(r); f.setSize(300,220); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** Swing is Java's GUI toolkit. `JFrame` is a top-level window; `JButton` generates an action event; `ActionListener` handles button clicks.