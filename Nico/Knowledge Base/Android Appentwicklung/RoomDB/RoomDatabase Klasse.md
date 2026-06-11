---
Fach: "[[AWM]]"
Thema:
  - "[[RoomDB]]"
---
Diese Art der Klasse sollte in jeder App nur **einmal** vorkommen. Sie regelt den Zugriff auf **alle** Tabellen. Diese Klasse erbt von `RoomDatabase`:  
  
**Beispiel:**
```java 
import android.content.Context;  
  
import androidx.room.Database;  
import androidx.room.Room;  
import androidx.room.RoomDatabase;  
  
  
@Database(entities = {Article.class}, version = 1)  
public abstract class AppRoomDatabase extends RoomDatabase {  
    private static  AppRoomDatabase roomDb =null;  
    public abstract ArticleDao articleDao();
  
    static AppRoomDatabase getDatabase(final Context context) {  
        if (roomDb == null) {  
            synchronized (AppRoomDatabase.class) {  
                if (roomDb == null) {  
                    roomDb = Room.databaseBuilder(context.getApplicationContext(), AppRoomDatabase.class, "article_database").build();  
                }  
            }  
        }  
        return roomDb;  
    }  
}
```