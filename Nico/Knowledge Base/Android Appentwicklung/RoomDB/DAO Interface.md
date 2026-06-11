---
Fach: "[[AWM]]"
Thema:
  - "[[RoomDB]]"
---
In dieser **Interface** wird der **Datenzugriff** realisiert. Dafür werden **Methoden** und dessen **Ergebnisse** definiert. Für die **SQL-Statements** werden wieder **Annotationen** verwendet.  

| **Annotation** | **Wo**        | **Bedeutung**                                                                                |
| -------------- | ------------- | -------------------------------------------------------------------------------------------- |
| `@Dao`         | vor Interface | Legt fest das es ein DAO-Interface ist                                                       |
| `@Insert`      | vor Methode   | Die Methode ist die Insert Methode                                                           |
| `@Query()`     | vor Methode   | die Folgende Methode mach eine Query mit dem Statement "" (Parameter werdenmit `:` übergeben |
|                |               |                                                                                              |
|                |               |                                                                                              |
**Beispiel:**  
```java
import androidx.lifecycle.LiveData;  
import androidx.room.*;  
  
import java.util.List;  
  
@Dao  
public interface ArticleDao {  
    @Insert  
    void insertArticle(Article article);  
  
    @Query("SELECT * FROM article WHERE article_name = :name")  
    List<Article> findArticle(String name);  
  
    @Query("DELETE FROM article WHERE article_name = :name")  
    void deleteArticle(String name);  
  
    @Query("SELECT * FROM article")  
    LiveData<List<Article>> getAllArticles();  
}
```
