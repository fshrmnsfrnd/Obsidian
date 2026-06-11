---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
Ein `RecyclerView` ermöglicht die effiziente Darstellung großer Datenmengen. Um Daten in einem `RecyclerView` anzuzeigen, müssen Sie zwei Dinge tun: 
1. Mehrere Daten-Items müssen als Liste zur Verfügung gestellt werden. 
2. Für die Anzeige eines Daten-Items muss ein Layout festgelegt werden.
>Der `RecyclerView` verwendet (recycelt) pro Daten-Item das definierte Layout und zeigt es an. Wenn ein Daten-Item vom Bildschirm gescrollt wird, zerstört der `RecyclerView` seine Darstellung nicht. Stattdessen wird das Layout für neue, nun sichtbare Elemente wiederverwendet. Diese Wiederverwendung verbessert die Leistung und die Reaktionsfähigkeit Ihrer App erheblich und reduziert so den Stromverbrauch.
# Wichtige Klassen 
Folgende Klassen arbeiten zusammen, damit der `RecyclerView` die Daten dynamisch anzeigen kann: 
- Der **RecyclerView** ist das Widget, das die einzelnen Daten-Items mit dem Detail-Layout anzeigt. Der `RecyclerView` erbt von der Klasse `ViewGroup`. Die Klasse `RecyclerView` kann also wie ein `View` verwendet werden. Ziehen Sie den `RecyclerView` einfach auf eine Aktivität. 
- Die **Adapter-Klasse** (EanAdapter) enthält als innere Klasse eine projektspezifische `ViewHolderKlasse` (EanViewHolder) . Die `ViewHolder`-Klasse erbt von `RecyclerView.ViewHolder` 
- Die **Adapter-Klasse** selbst erbt von: `RecyclerView.Adapter<EanAdapter.EanViewHolder>` 
- Jedes einzelne **Daten-Item** wird nun durch ein spezielles `ViewHolder`-Objekt eingepackt und im `RecyclerView` angezeigt. 
- Für die Darstellung der einzelnen Daten-Items wird dem `RecyclerView` ein **Layout-Manager** zugeordnet.

# Beispiel
## Layout
**/res/layout/activity_main.xml**
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
        tools:context=".MainActivity">  
  
        <TextView            
	        android:id="@+id/itemTextSelected"  
            android:layout_width="285dp"  
            android:layout_height="26dp"  
            android:layout_marginTop="40dp"  
            android:text="itemTextSelected"  
            app:layout_constraintEnd_toEndOf="parent"  
            app:layout_constraintStart_toStartOf="parent"  
            app:layout_constraintTop_toTopOf="parent" />  
  
        <TextView            
	        android:id="@+id/itemValueSelected"  
            android:layout_width="234dp"  
            android:layout_height="22dp"  
            android:layout_marginTop="20dp"  
            android:text="itemValueSelected"  
            app:layout_constraintEnd_toEndOf="parent"  
            app:layout_constraintHorizontal_bias="0.497"  
            app:layout_constraintStart_toStartOf="parent"  
            app:layout_constraintTop_toBottomOf="@+id/itemTextSelected" />  
  
        <androidx.recyclerview.widget.RecyclerView            
	        android:id="@+id/RecyclerView"  
            android:layout_width="376dp"  
            android:layout_height="250dp"  
            android:layout_marginTop="80dp"  
            android:background="#FFFFFF"  
            app:layout_constraintTop_toBottomOf="@+id/itemValueSelected"  
            tools:layout_editor_absoluteX="17dp" />  
    </androidx.constraintlayout.widget.ConstraintLayout>  
</androidx.coordinatorlayout.widget.CoordinatorLayout>
```

**/res/layout/item_layout.xml**
```xml
<?xml version="1.0" encoding="utf-8"?>  
<androidx.constraintlayout.widget.ConstraintLayout 
	xmlns:android="http://schemas.android.com/apk/res/android"  
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

## RecyclerViewListener
**/app/.../RecyclerViewListener**
```java
public interface RecyclerViewListener {  
    void onItemSelected(int position);  
}
```

## ItemEntity
**/app/.../ItemEntity**
```java
public class ItemEntity {  
    private String text;  
    private String value;  
  
    public ItemEntity(String text, String value) {  
        this.text = text;  
        this.value = value;  
    }  
  
    public String getText() {return text;  }  
    public void setText(String text) {this.text = text;}  
  
    public String getValue() {return value;}  
    public void setValue(String value) {this.value = value;}  
}
```
## AdapterClass
**/app/.../AdapterClass**
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
    public ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {  
        ItemLayoutBinding binding;  
        LayoutInflater inflater = LayoutInflater.from(parent.getContext());  
        binding = ItemLayoutBinding.inflate(inflater,parent,false);  
        return new ViewHolder(binding,listener);  
    }  
  
    @Override  
    public void onBindViewHolder(@NonNull ViewHolder holder, int position) {  
        //Daten-Objekt aus Liste ermitteln  
        ItemEntity item = itemList.get(position);  
        //Werte des Datenobjektes in ViewHolder-Objekt schreiben  
        holder.binding.itemText.setText(item.getText());  
        holder.binding.itemValue.setText(item.getValue());  
    }  
  
    @Override  
    public int getItemCount() {  
        return itemList == null ? 0 : itemList.size();  
    }  
  
    static class ViewHolder extends RecyclerView.ViewHolder {  
        ItemLayoutBinding binding;  
        //Konstruktor  
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

## MainActivity
**/app/.../MainActivity**
```java
import android.os.Bundle;
import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.recyclerview.widget.LinearLayoutManager;
import java.util.ArrayList;
import de.ts.btin2.recyclerviewuebungka.databinding.ActivityMainBinding;
  
public class MainActivity extends AppCompatActivity {
    private ActivityMainBinding binding;
    private ArrayList<ItemEntity> itemList = new ArrayList<>();
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        EdgeToEdge.enable(this);  
        binding = ActivityMainBinding.inflate(getLayoutInflater());  
        setContentView(binding.getRoot());  
        itemList.add(new ItemEntity("a", "1"));  
        itemList.add(new ItemEntity("b", "2"));  
        itemList.add(new ItemEntity("c", "3"));  
  
        binding.RecyclerView.setLayoutManager(new LinearLayoutManager(getApplicationContext()));  
  
        RecyclerViewListener listener = new RecyclerViewListener() {  
            @Override  
            public void onItemSelected(int position) {  
                ItemEntity item = itemList.get(position);  
                binding.itemTextSelected.setText(item.getText());  
                binding.itemValueSelected.setText(item.getValue());  
            }  
        };  
  
        binding.RecyclerView.setAdapter(new AdapterClass(itemList,listener));  
    }  
}
```