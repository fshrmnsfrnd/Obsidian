---
Fach: "[[AWM]]"
Thema:
  - "[[RoomDB]]"
---
**Reihenfolge der Aufrufe:**
```
MainActivity.addItem(<ItemEntity>) ->
MainViewModel.insertItem(<ItemEntity>) -> 
repository.insertItem(<ItemEntity>) ->
ItemDao.insertItem(<ItemEntity>) ->
@Insert(<ItemEntity>)
```
# Layout
---
**item_layout**
---
```xml
<?xml version="1.0" encoding="utf-8"?>  
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:layout_width="match_parent"  
    android:layout_height="wrap_content">  
  
    <TextView        
	    android:id="@+id/itemText"  
        android:layout_width="218dp"  
        android:layout_height="18dp"  
        android:text="Text"  
        app:layout_constraintEnd_toEndOf="parent"  
        app:layout_constraintStart_toStartOf="parent"  
        app:layout_constraintTop_toTopOf="parent" />  
  
    <TextView        
	    android:id="@+id/itemValue"  
        android:layout_width="216dp"  
        android:layout_height="23dp"  
        android:text="Value"  
        app:layout_constraintEnd_toEndOf="parent"  
        app:layout_constraintStart_toStartOf="parent"  
        app:layout_constraintTop_toBottomOf="@+id/itemText" />  
</androidx.constraintlayout.widget.ConstraintLayout>
```

**activity_main.xml**
---
```xml
<?xml version="1.0" encoding="utf-8"?>  
<androidx.coordinatorlayout.widget.CoordinatorLayout  
    xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent">  
  
    <androidx.constraintlayout.widget.ConstraintLayout        
	    android:id="@+id/main"  
        android:layout_width="match_parent"  
        android:layout_height="match_parent"  
        app:layout_anchor="@+id/main"  
        app:layout_anchorGravity="center"  
        tools:context=".MainActivity">  
  
        <TextView            
	        android:id="@+id/itemIdSelected"  
            android:layout_width="285dp"  
            android:layout_height="26dp"  
            android:layout_marginTop="40dp"  
            android:text="itemIdSelected"  
            app:layout_constraintEnd_toEndOf="parent"  
            app:layout_constraintStart_toStartOf="parent"  
            app:layout_constraintTop_toTopOf="parent" />  
  
        <androidx.recyclerview.widget.RecyclerView            
	        android:id="@+id/RecyclerView"  
            android:layout_width="376dp"  
            android:layout_height="250dp"  
            android:layout_marginTop="28dp"  
            android:background="#FFFFFF"  
            app:layout_constraintTop_toBottomOf="@+id/btnFind"  
            tools:layout_editor_absoluteX="17dp" />  
  
        <Button            
	        android:id="@+id/btnAdd"  
            android:layout_width="wrap_content"  
            android:layout_height="wrap_content"  
            android:onClick="addItem"  
            android:text="Add"  
            app:layout_constraintStart_toStartOf="parent"  
            app:layout_constraintTop_toBottomOf="@+id/itemValueSelected" />  
  
        <Button            
	        android:id="@+id/btnFind"  
            android:layout_width="wrap_content"  
            android:layout_height="wrap_content"  
            android:layout_marginStart="72dp"  
            android:onClick="findItem"  
            android:text="Find"  
            app:layout_constraintStart_toEndOf="@+id/btnAdd"  
            app:layout_constraintTop_toBottomOf="@+id/itemValueSelected" />  
  
        <Button            
	        android:id="@+id/btnDelete"  
            android:layout_width="wrap_content"  
            android:layout_height="wrap_content"  
            android:onClick="deleteItem"  
            android:text="Delete"  
            app:layout_constraintEnd_toEndOf="parent"  
            app:layout_constraintHorizontal_bias="0.565"  
            app:layout_constraintStart_toEndOf="@+id/btnFind"  
            app:layout_constraintTop_toBottomOf="@+id/itemValueSelected" />  
  
        <EditText            
	        android:id="@+id/itemValueSelected"  
            android:layout_width="wrap_content"  
            android:layout_height="wrap_content"  
            android:layout_marginTop="1dp"  
            android:ems="10"  
            android:inputType="text"  
            android:text="itemValueSelected"  
            app:layout_constraintEnd_toEndOf="parent"  
            app:layout_constraintStart_toStartOf="parent"  
            app:layout_constraintTop_toBottomOf="@+id/itemIdSelected" />  
  
    </androidx.constraintlayout.widget.ConstraintLayout>  
</androidx.coordinatorlayout.widget.CoordinatorLayout>
```

# Dependencies
---
![[gradle_config]]
# AppRoomDatabase
---
```java
import android.content.Context;  
import androidx.room.Database;  
import androidx.room.Room;  
import androidx.room.RoomDatabase;  
  
@Database(entities = {ItemEntity.class}, version = 1, exportSchema = false)  
public abstract class AppRoomDatabase extends RoomDatabase {  
    private static AppRoomDatabase roomDb = null;  
    public abstract ItemDao itemDao();  
  
    static AppRoomDatabase getDatabase(final Context context) {  
        if (roomDb == null) {  
            synchronized (AppRoomDatabase.class) {  
                if (roomDb == null) {  
                    roomDb = Room.databaseBuilder(context.getApplicationContext(), AppRoomDatabase.class, "item_database").build();  
                }  
            }  
        }  
        return roomDb;  
    }  
}
```
# ItemEntity
---
```java
import androidx.room.Entity;  
import androidx.annotation.NonNull;  
import androidx.room.ColumnInfo;  
import androidx.room.PrimaryKey;  
  
@Entity(tableName = "item")  
public class ItemEntity {  
    @PrimaryKey(autoGenerate = true)  
    @NonNull  
    @ColumnInfo(name = "item_id")  
    private int id;
    
    @ColumnInfo(name = "item_value")  
    private String value;  
	
    public ItemEntity(String value) {this.value = value;}  
	
    public int getId() {return id;}  
    public void setId(int id) {this.id = id;}  
	
    public String getValue() {return value;}  
    public void setValue(String value) {this.value = value;}  
}
```
# RecyclerViewListener
---
```java
public interface RecyclerViewListener {  
    void onItemSelected(int position);  
}
```
# ItemDao
---
```java
import androidx.lifecycle.LiveData;  
import androidx.room.Dao;  
import androidx.room.Insert;  
import androidx.room.Query;  
import java.util.List;  
  
@Dao  
public interface ItemDao {  
    @Insert  
    void insertItem(ItemEntity item);  
    @Query("SELECT * FROM item WHERE item_value = :value")  
    List<ItemEntity> findItem(String value);  
	
    @Query("DELETE FROM item WHERE item_id = :id")  
    void deleteItem(String id);  
	
    @Query("SELECT * FROM item")  
    LiveData<List<ItemEntity>> getAllItems();  
}
```
# ItemRepository
---
```java
import android.app.Application;  
import android.os.Handler;  
import android.os.Looper;  
import android.os.Message;  
import androidx.lifecycle.LiveData;  
import androidx.lifecycle.MutableLiveData;  
import java.util.List;  
import java.util.concurrent.ExecutorService;  
import java.util.concurrent.Executors;  
  
public class ItemRepository {  
    private final MutableLiveData<List<ItemEntity>> searchResults= new MutableLiveData<>();  
    private List<ItemEntity> results;  
    private final LiveData<List<ItemEntity>> allItems;  
    private final ItemDao itemDao;  
	  
    public ItemRepository(Application application) {  
        AppRoomDatabase db;  
        db = AppRoomDatabase.getDatabase(application);  
        itemDao = db.itemDao();  
        allItems = itemDao.getAllItems();  
    }  
	  
    Handler handler = new Handler(Looper.getMainLooper()) {  
        @Override  
        public void handleMessage(Message msg) {  
            searchResults.setValue(results);  
        }  
    };  
	  
    public void insertItem(ItemEntity newItem) {  
        ExecutorService executor = Executors.newSingleThreadExecutor();  
        executor.submit(() -> {itemDao.insertItem(newItem);});  
        executor.shutdown();  
    }  
	  
    public void deleteItem(String id) {  
        ExecutorService executor = Executors.newSingleThreadExecutor();  
        executor.submit(() -> {itemDao.deleteItem(id);});  
        executor.shutdown();  
    }  
	  
    public void findItem(String value) {  
        ExecutorService executor = Executors.newSingleThreadExecutor();  
        executor.submit(() -> {  
            results = itemDao.findItem(value);  
            handler.sendEmptyMessage(0);  
        });  
        executor.shutdown();  
    }  
	  
    public LiveData<List<ItemEntity>> getAllItems() {return allItems;}  
    public MutableLiveData<List<ItemEntity>> getSearchResults() {return searchResults;}  
}
```
# AdapterClass
---
```java
import de.ts.btin2.recyclerviewuebungka.databinding.ItemLayoutBinding;  
import android.view.LayoutInflater;  
import android.view.View;  
import android.view.ViewGroup;  
import androidx.annotation.NonNull;  
import androidx.recyclerview.widget.RecyclerView;  
import java.util.List;  
  
public class AdapterClass extends RecyclerView.Adapter<AdapterClass.ViewHolder>{  
    private List<ItemEntity> itemList;  
    private RecyclerViewListener listener;  
	  
    public AdapterClass(List<ItemEntity> itemList, RecyclerViewListener listener) {  
        this.listener = listener;  
        this.itemList = itemList;  
    }  
	  
    @NonNull  
    @Override    
    public ViewHolder onCreateViewHolder(ViewGroup parent, int viewType) {  
        ItemLayoutBinding binding;  
        LayoutInflater inflater = LayoutInflater.from(parent.getContext());  
        binding = ItemLayoutBinding.inflate(inflater,parent,false);  
        return new ViewHolder(binding,listener);  
    }  
	  
    @Override  
    public void onBindViewHolder(@NonNull ViewHolder holder, int position) {   
        ItemEntity item = itemList.get(position);  
        holder.binding.itemText.setText(String.valueOf(item.getId()));  
        holder.binding.itemValue.setText(item.getValue());  
    }  
	  
    @Override  
    public int getItemCount() {  
        return itemList == null ? 0 : itemList.size();  
    }  
	  
    public void setItemList(List<ItemEntity> items){  
        this.itemList = items;  
        notifyDataSetChanged();  
    }  
	  
    static class ViewHolder extends RecyclerView.ViewHolder {  
        ItemLayoutBinding binding;  
        ViewHolder(ItemLayoutBinding binding, RecyclerViewListener listener) {  
            super(binding.getRoot());  
            this.binding = binding;  
            itemView.setOnClickListener(new View.OnClickListener() {  
                @Override  
                public void onClick(View view) {  
                    listener.onItemSelected(getAdapterPosition());  
                }  
            });  
        }  
    }  
}
```
# MainViewModel
---
```java
import android.app.Application;  
import androidx.annotation.NonNull;  
import androidx.lifecycle.AndroidViewModel;  
import androidx.lifecycle.LiveData;  
import androidx.lifecycle.MutableLiveData;  
import java.util.List;  
  
public class MainViewModel extends AndroidViewModel {  
    private ItemRepository repository;  
    private LiveData<List<ItemEntity>> allItems;  
    private MutableLiveData<List<ItemEntity>> searchResults;  
  
    public MainViewModel(@NonNull Application application) {  
        super(application);  
        repository = new ItemRepository(application);  
        allItems = repository.getAllItems();  
        searchResults = repository.getSearchResults();  
    }  
  
    public MutableLiveData<List<ItemEntity>> getSearchResults() {return searchResults;}  
  
    public LiveData<List<ItemEntity>> getAllItems() {return allItems;}  
  
    public void insertItem(ItemEntity item) {repository.insertItem(item);}  
  
    public void findItem(String value) {repository.findItem(value);}  
  
    public void deleteItem(String id) {repository.deleteItem(id);}  
}
```
# MainActivity
---
```java
import android.os.Bundle;  
import android.view.View;  
import androidx.activity.EdgeToEdge;  
import androidx.appcompat.app.AppCompatActivity;  
import androidx.recyclerview.widget.LinearLayoutManager;  
import java.util.ArrayList;  
import de.ts.btin2.recyclerviewuebungka.databinding.ActivityMainBinding;  
  
public class MainActivity extends AppCompatActivity {  
    private MainViewModel mViewModel;  
    private AdapterClass adapter;  
    private ActivityMainBinding binding;  
    private ArrayList<ItemEntity> itemList = new ArrayList<>();  
	  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        EdgeToEdge.enable(this);  
        binding = ActivityMainBinding.inflate(getLayoutInflater());  
        setContentView(binding.getRoot());  
		  
        RecyclerViewListener listener = new RecyclerViewListener() {  
            @Override  
            public void onItemSelected(int position) {  
                if (position >= 0 && position < itemList.size()) {  
                    ItemEntity item = itemList.get(position);  
                    binding.itemIdSelected.setText(String.valueOf(item.getId()));  
                    binding.itemValueSelected.setText(item.getValue());  
                }  
            }  
        };  
		  
        binding.RecyclerView.setLayoutManager(new LinearLayoutManager(getApplicationContext()));  
        adapter = new AdapterClass(itemList, listener);  
        binding.RecyclerView.setAdapter(adapter);  
		  
        mViewModel = new MainViewModel(getApplication());  
        mViewModel.getAllItems().observe(this, items -> {  
            itemList.clear();  
            if (items != null) {  
                itemList.addAll(items);  
            }  
            adapter.setItemList(itemList);  
        });  
        mViewModel.getSearchResults().observe(this,items -> {  
            if (!items.isEmpty())  {  
                binding.itemIdSelected.setText(String.valueOf(items.get(0).getId()));  
                binding.itemValueSelected.setText(items.get(0).getValue());  
            } else {  
                binding.itemIdSelected.setText("kein Treffer");  
            }  
        });  
    }  
	  
    public void addItem(View v){  
        String id = binding.itemIdSelected.getText().toString();  
        String value = binding.itemValueSelected.getText().toString();  
		  
        if (!value.isEmpty()) {  
            ItemEntity item = new ItemEntity(value);  
            mViewModel.insertItem(item);  
            //clearFields();  
        } else {  
            binding.itemIdSelected.setText("Unvollständige Information");  
        }  
    }  
	  
    public void findItem(View view) {  
        mViewModel.findItem(binding.itemValueSelected.getText().toString());  
    }  
	  
    public void deleteItem(View view) {  
        mViewModel.deleteItem(binding.itemIdSelected.getText().toString());  
        //clearFields();  
    }  
}
```