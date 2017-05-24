# navigation-app
Organize your app's structure according to the content and tasks you want users to see. Focus attention on important destinations by displaying them in tabs or in the side navigation, and de-emphasize inessential content by displaying it in less prominent locations.

## Creating a Navigation Drawer

The navigation drawer is a panel that displays the app’s main navigation options on the left edge of the screen. It is hidden most of the time, but is revealed when the user swipes a finger from the left edge of the screen or, while at the top level of the app, the user touches the app icon in the action bar.

### dependencies

```java

compile 'com.android.support:design:25.3.1'

```


#### Create a Navigation Drawer Layout

##### activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.v4.widget.DrawerLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/drawer_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fitsSystemWindows="true">

    <RelativeLayout
        android:id="@+id/main_content"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">

        <android.support.v7.widget.Toolbar
            android:id="@+id/tool_bar"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_alignParentTop="true"
            android:background="@color/colorPrimary"
            android:minHeight="?attr/actionBarSize"
            app:theme="@style/ThemeOverlay.AppCompat.Dark.ActionBar" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="NAVIGATION MENU"
        android:textSize="30sp"
        android:textColor="#3E2723"
        android:layout_centerInParent="true"/>

    </RelativeLayout>

    <android.support.design.widget.NavigationView
        android:id="@+id/main_drawer"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:itemIconTint="#4CAF50"
        app:itemTextColor="#3E2723"
        app:headerLayout="@layout/header_layout"
        app:menu="@menu/main_menu"
        android:layout_gravity="start">

    </android.support.design.widget.NavigationView>


</android.support.v4.widget.DrawerLayout>


```

##### header_layout.xml

```xml

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    android:orientation="vertical"
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/drawer_layout"
    android:layout_width="match_parent"
    android:layout_height="190dp"
    android:background="@drawable/header_background"
   >

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="56dp"
        android:layout_alignParentBottom="true"
        android:orientation="vertical"
        android:paddingBottom="15dp"
        android:paddingLeft="15dp">
        <TextView
            android:id="@+id/nameText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Mohammad Rafique"
            android:layout_weight="1"
            android:gravity="bottom"
            android:textSize="14dp"
            android:textColor="#FFFFFF"
            android:fontFamily="sans-serif-medium"/>

        <TextView
            android:id="@+id/emailText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="rafique28mr@gmail.com"
            android:layout_weight="1"
            android:gravity="bottom"
            android:textSize="14dp"
            android:textColor="#FFFFFF"
            android:fontFamily="sans-serif"/>

    </LinearLayout>
</RelativeLayout>



```

##### main_menu.xml

```xml

<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">


    <group android:id="@+id/number1">
        <item
            android:id="@+id/item_one"
            android:checkable="true"
            android:icon="@drawable/num1"
            android:title="Number One" />

        <item
            android:id="@+id/item_two"
            android:checkable="true"
            android:icon="@drawable/num2"
            android:title="Number Two" />
        <item
            android:id="@+id/item_three"
            android:checkable="true"
            android:icon="@drawable/num3"
            android:title="Number Three" />

    </group>

    <group android:id="@+id/number2">

        <item
            android:id="@+id/item_four"
            android:checkable="true"
            android:icon="@drawable/num4"
            android:title="Number Four" />
        <item
            android:id="@+id/item_five"
            android:checkable="true"
            android:icon="@drawable/num5"
            android:title="Number Five" />
        <item
            android:id="@+id/item_six"
            android:checkable="true"
            android:icon="@drawable/num6"
            android:title="Number Six" />

    </group>

    <group android:id="@+id/number3">

        <item
            android:id="@+id/item_seven"
            android:checkable="true"
            android:icon="@drawable/num7"
            android:title="Number Seven" />
        <item
            android:id="@+id/item_eight"
            android:checkable="true"
            android:icon="@drawable/num8"
            android:title="Number Eight" />
        <item
            android:id="@+id/item_nine"
            android:checkable="true"
            android:icon="@drawable/num9"
            android:title="Number Nine" />

    </group>


</menu>


```

##### MainActivity.java


```xml

package com.example.thedeveloper.navigationdrawerapp;

import android.os.Bundle;
import android.support.v4.widget.DrawerLayout;
import android.support.v7.app.ActionBarDrawerToggle;
import android.support.v7.app.AppCompatActivity;
import android.support.v7.widget.Toolbar;

public class MainActivity extends AppCompatActivity {

    private DrawerLayout drawerLayout;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Toolbar toolbar = (Toolbar) findViewById(R.id.tool_bar);
        toolbar.setTitle("Navigation App");
        setSupportActionBar(toolbar);
        drawerLayout = (DrawerLayout) findViewById(R.id.drawer_layout);

        //NavigationView navigationView = (NavigationView) findViewById(R.id.main_drawer);

        ActionBarDrawerToggle toggle = new ActionBarDrawerToggle(MainActivity.this,drawerLayout , toolbar ,R.string.open,R.string.close);
        drawerLayout.addDrawerListener(toggle);
        toggle.syncState();
    }
}

```


### Screenshot App


<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/28509637/26402275/0ac495f6-40a3-11e7-9b36-23949dd64123.png" width="400"/>
   <img src="https://cloud.githubusercontent.com/assets/28509637/26402276/0b007d5a-40a3-11e7-9664-004d27461843.png" width="400"/>
</p>



#### style.xml


```xml
<resources>

    <!-- Base application theme. -->
<style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
        
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
        <item name="android:statusBarColor">@android:color/transparent</item>

</style>

</resources>
```



