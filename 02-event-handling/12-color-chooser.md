# 12. JColorChooser

**Aim:** Change a panel background using a color chooser.

**Algorithm:** Create panel and button → open chooser on click → apply chosen color.

**Pseudocode:** color = showDialog → if color selected, set panel background.

**Flowchart:** Start → Click Choose Color → Select color → Apply background → Stop.

```java
import javax.swing.*;
import java.awt.*;
public class ColorChooserDemo {
 public static void main(String[] a) {
  JFrame f=new JFrame("Color Chooser"); JPanel p=new JPanel(); JButton b=new JButton("Choose Color");
  b.addActionListener(e->{Color c=JColorChooser.showDialog(f,"Pick a color",p.getBackground());if(c!=null)p.setBackground(c);});
  p.add(b); f.add(p); f.setSize(350,200); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** `JColorChooser` provides a standard color-selection dialog. `Color` represents an RGB color.