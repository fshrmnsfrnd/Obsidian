---
Fach: "[[AWM]]"
Thema:
  - "[[RoomDB]]"
---
Hier wird die Interaktion mit der Room-Datenbank sicher gestellt. Auf das **Repository** wird über das **ViewModel** zugegriffen. Zur Datenabfrage wird das **DAO-Interface** verwendet.  
  
Die **Datenoperationen** werden für gewöhnlich in eigenen Threads ausgeführt. Um die Ergebnisse zurück in den Main-Thread zu holen benötigt man einen `Handler` und `Looper`.  
Damit Methoden in neuen Threads ausgeführt werden können wird die Methode `newSingleThreadExecuter()` aus der Klasse `Executer` verwendet.  
  
**Beispiel:**  
```java
import android.app.Application;  
import android.os.Handler;  
import android.os.Looper;  
import android.os.Message;  
import java.util.concurrent.ExecutorService;  
import java.util.concurrent.Executors;  
import androidx.lifecycle.MutableLiveData; import java.util.List;  
import androidx.lifecycle.LiveData;  
  
public class ArticleRepository {  
    private final MutableLiveData<List<Article>> searchResults= new MutableLiveData<>();  
    private List<Article> results;  
    private final LiveData<List<Article>> allArticles;  
    private final ArticleDao articleDao;  
  
    Handler handler = new Handler(Looper.getMainLooper()) {  
        @Override  
        public void handleMessage(Message msg) {  
            searchResults.setValue(results);  
        }  
    };  
  
    public ArticleRepository(Application application) {  
        AppRoomDatabase db;  
        db = AppRoomDatabase.getDatabase(application);  
        articleDao = db.articleDao();  
        allArticles = articleDao.getAllArticles();  
    }  
  
    public void insertArticle(Article newArticle) {  
        ExecutorService executor = Executors.newSingleThreadExecutor();  
        executor.submit(() -> { articleDao.insertArticle(newArticle);});  
        executor.shutdown();  
    }  
  
    public void deleteArticle(String name) {  
        ExecutorService executor = Executors.newSingleThreadExecutor();  
        executor.submit(() -> { articleDao.deleteArticle(name);});  
        executor.shutdown();  
    }  
  
    public void findArticle(String name) {  
        ExecutorService executor = Executors.newSingleThreadExecutor();  
        executor.submit(() -> {  
            results = articleDao.findArticle(name);  
            handler.sendEmptyMessage(0);  
        });  
        executor.shutdown();  
    }  
  
    //Getter
    public LiveData<List<Article>> getAllArticles() {  
        return allArticles;  
    }  
    public MutableLiveData<List<Article>> getSearchResults() {  
        return searchResults;  
    }  
}
```