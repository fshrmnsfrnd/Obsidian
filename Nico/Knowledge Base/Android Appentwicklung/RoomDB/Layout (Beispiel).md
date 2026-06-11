---
Fach: "[[AWM]]"
Thema:
  - "[[RoomDB]]"
---
# /res/layout/activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_margin="10pt"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <TableLayout
        android:id="@+id/inputFields"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content">

        <TableRow
            android:layout_width="match_parent"
            android:layout_height="match_parent">

            <TextView
                android:id="@+id/txtArticleNr"
                android:layout_width="110dp"
                android:layout_height="wrap_content"
                android:text="@string/ArticleNumber"
                android:textColor="@color/black"
                android:textStyle="bold" />

            <EditText
                android:id="@+id/inputArticleNr"
                android:layout_width="302dp"
                android:layout_height="wrap_content"
                android:ems="10"
                android:inputType="textPersonName" />
        </TableRow>

        <TableRow
            android:layout_width="match_parent"
            android:layout_height="match_parent">

            <TextView
                android:id="@+id/tvArticleName"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="@string/ArticleName"

                android:textColor="@color/black"
                android:textStyle="bold" />

            <EditText
                android:id="@+id/inputArticleName"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:ems="10"
                android:inputType="textPersonName" />
        </TableRow>

        <TableRow
            android:layout_width="match_parent"
            android:layout_height="match_parent">

            <TextView
                android:id="@+id/tvQuantity"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="@string/ArticleQuantity"
                android:textColor="@color/black"
                android:textStyle="bold" />

            <EditText
                android:id="@+id/inputArticleQuantity"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:ems="10"
                android:inputType="textPersonName" />

        </TableRow>

    </TableLayout>

    <LinearLayout
        android:id="@+id/controlsCRUD"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:textAlignment="center">

        <Button
            android:id="@+id/btnAdd"
            style="@style/Widget.AppCompat.Button.Borderless"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:onClick="addArticle"
            android:text="@string/ArticleNew"
            android:textColor="@color/design_default_color_primary"
            android:textStyle="bold" />

        <Button
            android:id="@+id/btnFind"
            style="@style/Widget.AppCompat.Button.Borderless"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:onClick="findArticles"
            android:text="@string/ArticleFind"
            android:textColor="@color/design_default_color_primary"
            android:textStyle="bold" />

        <Button
            android:id="@+id/btnDelete"
            style="@style/Widget.AppCompat.Button.Borderless"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:onClick="deleteArticle"
            android:text="@string/ArticleDelete"
            android:textAlignment="center"
            android:textColor="@color/design_default_color_primary"
            android:textStyle="bold" />
    </LinearLayout>

    <LinearLayout
        android:id="@+id/headerArticelList"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <TextView
            android:id="@+id/tvArticelList"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_margin="10pt"
            android:fontFamily="sans-serif"
            android:text="@string/ArticleListHeader"
            android:textSize="20sp"
            android:textStyle="bold" />
    </LinearLayout>

    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/articleList"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        tools:itemCount="10">

    </androidx.recyclerview.widget.RecyclerView>

</LinearLayout>
```
# /res/layout/article_list_item.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical">

    <TextView
        android:id="@+id/articleItemName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/purple_200"
        android:text="Artikelname"
        android:textColor="@color/black"
        android:textSize="18sp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/articleItemQuantity"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@android:color/background_light"
        android:text="Artikelanzahl"
        android:textColor="@color/black"
        android:textSize="16sp" />

</LinearLayout>
```