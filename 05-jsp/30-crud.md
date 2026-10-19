# 30. Search, Update and Delete

**Aim:** Perform CRUD operations using parameterized SQL.

**Algorithm:** Connect DB → choose operation → prepare SQL → bind values → execute → report affected rows.

**Pseudocode:** Search uses SELECT; update uses UPDATE; delete uses DELETE. Bind user values with PreparedStatement.

**Flowchart:** Start → Choose operation → Execute parameterized SQL → Show result → Stop.

**Core JDBC examples**
```java
// Search
PreparedStatement s=c.prepareStatement("SELECT * FROM students WHERE id=?");
s.setInt(1,id); ResultSet r=s.executeQuery();

// Update
PreparedStatement u=c.prepareStatement("UPDATE students SET marks=? WHERE id=?");
u.setInt(1,marks); u.setInt(2,id); u.executeUpdate();

// Delete
PreparedStatement d=c.prepareStatement("DELETE FROM students WHERE id=?");
d.setInt(1,id); d.executeUpdate();
```

**Viva:** CRUD means Create, Read, Update, Delete. SELECT uses `executeQuery()`; INSERT/UPDATE/DELETE use `executeUpdate()`. PreparedStatement helps prevent SQL injection. Validate input and restrict database permissions.