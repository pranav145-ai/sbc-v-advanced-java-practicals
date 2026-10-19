# 6. Menu-Driven Text Editor

**Aim:** Create a text area with File menu actions.

**Algorithm:** Create frame and text area → add menu → wire New and Exit → display.

**Pseudocode:** If New, clear text; if Exit, close application.

**Flowchart:** Start → Open editor → Choose menu item → Perform action → Stop/continue.

```java
import javax.swing.*;
public class MenuEditor {
 public static void main(String[] a) {
  JFrame f=new JFrame("Editor"); JTextArea t=new JTextArea();
  JMenuBar bar=new JMenuBar(); JMenu file=new JMenu("File");
  JMenuItem n=new JMenuItem("New"), exit=new JMenuItem("Exit");
  n.addActionListener(e->t.setText("")); exit.addActionListener(e->f.dispose());
  file.add(n); file.add(exit); bar.add(file); f.setJMenuBar(bar); f.add(new JScrollPane(t));
  f.setSize(400,300); f.setDefaultCloseOperation(3); f.setVisible(true);
 }
}
```

**Viva:** `JMenuBar` holds menus, `JMenu` holds items, `JMenuItem` represents a selectable command.