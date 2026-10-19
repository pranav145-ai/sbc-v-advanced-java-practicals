# 8. MouseListener

**Aim:** Handle mouse click, enter and exit events.

**Algorithm:** Create label → implement MouseListener → update label on events.

**Pseudocode:** On mouseClicked set text to “Clicked”; on enter/exit update text.

**Flowchart:** Start → Move/click mouse → Event fires → Update label → Stop.

```java
import javax.swing.*;
import java.awt.event.*;
public class MouseListenerDemo extends JFrame implements MouseListener {
 JLabel l=new JLabel("Use the mouse");
 MouseListenerDemo(){add(l);addMouseListener(this);setSize(300,150);setDefaultCloseOperation(3);setVisible(true);}
 public void mouseClicked(MouseEvent e){l.setText("Clicked");}
 public void mousePressed(MouseEvent e){} public void mouseReleased(MouseEvent e){}
 public void mouseEntered(MouseEvent e){l.setText("Entered");} public void mouseExited(MouseEvent e){l.setText("Exited");}
 public static void main(String[] a){new MouseListenerDemo();}
}
```

**Viva:** `MouseListener` has five methods: clicked, pressed, released, entered, exited.