---
Fach: "[[AWM]]"
Thema:
  - "[[RoomDB]]"
---
Diese Klasse hat folgende Aufgaben:  
- Jedes **Objekt** entspricht später einem **Datensatz**. Die Eigenschaften werden über **Getter** und **Setter** gelesen oder geändert  
- Hier wird das **Schema** der dazugehörigen Tabelle festgelegt. Dafür werden **Annotationen** verwendet  
Es gibt folgende Annotationen:  

|**Annotation**|Wo|Bedeutung|
|---|---|---|
|`@Entity(tableName = "tbl_name")`|vor Klasse|Legt den Namen der Tabelle fest (hier `tbl_name`)|
|`@PrimaryKey(autoGenerate = true)`|vor Eigenschaft|Legt den Primärschlüssel fest und er wird automatisch generiert|
|`@NonNull`|vor Eigenschaft|Spalte darf nicht `NULL` sein|
|`@ColumnInfo(name = "col_name")|vor eigenschaft|Spaltenname wird auf `col_name` gesetzt|
**Beispiel:**  
```java
import androidx.annotation.NonNull;
import androidx.room.ColumnInfo;
import androidx.room.Entity;
import androidx.room.PrimaryKey;

@Entity(tableName = "article")
public class Article{
    @PrimaryKey(autoGenerate = true)
    @NonNull
    @ColumnInfo(name = "article_id")
    private int id;
    @ColumnInfo(name = "article_name")
    private String name;
    @ColumnInfo(name = "article_quantity")
    private int quantity;
  
    public Article(String name, int quantity){
        this.name = name;  
        this.quantity = quantity;  
    }  
  
    public int getId(){return this.id;}
  
    public String getName(){return this.name;}
  
    public int getQuantity(){return this.quantity;}
  
    public void setId(int id){this.id = id;}  
  
    public void setName(String name){this.name = name;}  
  
    public void setQuantity(int quantity){this.quantity = quantity;}  
}
```