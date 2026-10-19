# 3. Layout Managers

**Aim:** Demonstrate FlowLayout, BorderLayout and GridLayout.

**Algorithm:** Create frame → choose layout → add components → display.

**Pseudocode:** Create window → set layout → add buttons → show.

**Flowchart:** Start → Create frame → Set layout → Add controls → Display → Stop.

```java
import javax.swing.*;
import java.awt.*;
public class LayoutDemo {
 public static void main(String[] a) {
  JFrame f=new JFrame("Layouts"); f.setLayout(new BorderLayout());
  f.add(new JButton("North"),BorderLayout.NORTH);
  f.add(new JButton("South"),BorderLayout.SOUTH);
  JPanel p=new JPanel(new GridLayout(1,2));
  p.add(new JButton("One")); p.add(new JButton("Two"));
  f.add(p,BorderLayout.CENTER);
  f.setSize(300,180); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** Layout managers arrange components automatically. FlowLayout places components sequentially; BorderLayout has five regions; GridLayout uses equal-sized cells.