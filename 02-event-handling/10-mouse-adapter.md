# 10. MouseAdapter

**Aim:** Handle a mouse click using MouseAdapter.

**Algorithm:** Create frame → add MouseAdapter → show click coordinates.

**Pseudocode:** On click, read x and y → display them.

**Flowchart:** Start → Click mouse → Read coordinates → Display → Stop.

```java
import javax.swing.*;
import java.awt.event.*;
public class MouseAdapterDemo {
 public static void main(String[] a) {
  JFrame f=new JFrame("Mouse Adapter"); JLabel l=new JLabel("Click inside the window");
  f.add(l); f.addMouseListener(new MouseAdapter(){public void mouseClicked(MouseEvent e){l.setText("x="+e.getX()+", y="+e.getY());}});
  f.setSize(300,180); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** Adapter classes provide empty implementations of listener methods. Override only the event method needed.