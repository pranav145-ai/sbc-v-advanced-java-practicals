# 4. Temperature Converter

**Aim:** Convert Celsius to Fahrenheit.

**Algorithm:** Read Celsius → compute F = C × 9/5 + 32 → display Fahrenheit.

**Pseudocode:** Input C → F=(C*9/5)+32 → Output F.

**Flowchart:** Start → Enter Celsius → Convert → Display Fahrenheit → Stop.

```java
import javax.swing.*;
public class TemperatureConverter {
 public static void main(String[] a) {
  JFrame f=new JFrame("Celsius to Fahrenheit");
  JTextField c=new JTextField(), out=new JTextField(); out.setEditable(false);
  JButton b=new JButton("Convert");
  JPanel p=new JPanel(); p.add(new JLabel("Celsius")); p.add(c); p.add(b); p.add(out);
  b.addActionListener(e->{try{out.setText(""+(Double.parseDouble(c.getText())*9/5+32));}catch(Exception ex){out.setText("Invalid");}});
  f.add(p); f.setSize(360,120); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** Formula is F = (C × 9/5) + 32. `setEditable(false)` prevents editing the output field.