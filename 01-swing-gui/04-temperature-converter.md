# 4. Celsius ↔ Fahrenheit Converter

**Aim:** Convert in both directions using Swing.

**Algorithm:** Enter temperature → choose conversion direction → apply formula → display result.

**Pseudocode:** C to F: F=C*9/5+32; F to C: C=(F-32)*5/9.

**Flowchart:** Start → Enter temperature → Choose direction → Calculate → Display → Stop.

```java
import javax.swing.*;
public class TemperatureConverter {
 public static void main(String[] a) {
  JFrame f=new JFrame("Temperature Converter");
  JTextField in=new JTextField(7),out=new JTextField(7);out.setEditable(false);
  JButton cf=new JButton("C to F"),fc=new JButton("F to C");
  cf.addActionListener(e->convert(in,out,true));
  fc.addActionListener(e->convert(in,out,false));
  JPanel p=new JPanel();p.add(in);p.add(cf);p.add(fc);p.add(out);
  f.add(p);f.setSize(380,120);f.setDefaultCloseOperation(3);f.setVisible(true);
 }
 static void convert(JTextField i,JTextField o,boolean c){try{double n=Double.parseDouble(i.getText());o.setText(""+(c?n*9/5+32:(n-32)*5/9));}catch(Exception e){o.setText("Invalid input");}}
}
```

**Viva:** Celsius to Fahrenheit: F=(C×9/5)+32. Fahrenheit to Celsius: C=(F−32)×5/9. ActionListener handles button clicks.