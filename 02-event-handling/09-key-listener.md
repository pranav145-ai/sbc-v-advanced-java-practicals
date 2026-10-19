# 9. KeyListener

**Aim:** Display the key typed by the user.

**Algorithm:** Create text field and label → attach KeyListener → update label on keyTyped.

**Pseudocode:** On keyTyped, show event character.

**Flowchart:** Start → Type key → Key event → Update label → Stop.

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
public class KeyListenerDemo {
 public static void main(String[] a) {
  JFrame f=new JFrame("Key Listener"); JTextField t=new JTextField(); JLabel l=new JLabel("Type here");
  t.addKeyListener(new KeyAdapter(){public void keyTyped(KeyEvent e){l.setText("Typed: "+e.getKeyChar());}});
  f.setLayout(new GridLayout(2,1)); f.add(t); f.add(l); f.setSize(280,120); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** Key events include pressed, released and typed. `KeyAdapter` avoids implementing unused listener methods.