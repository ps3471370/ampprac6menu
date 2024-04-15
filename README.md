# ampprac6menu
PRACTICAL NO.  6

Question : 
Create an android application for the following menu items ,the appropriate
toast should appear by clicking on the item:
• Settings
• Search
• Compose Email (make Compose Email item disabled )
• Feedback


MainActivity.java
package com.example.prac6;
import static com.example.prac6.R.*;

import android.graphics.drawable.ColorDrawable;
import android.net.nsd.NsdManager;
import android.os.Bundle;

import android.view.Menu;
import android.view.MenuInflater;
import android.view.MenuItem;
import android.widget.Toast;
import androidx.activity.EdgeToEdge;
import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;


public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);
        getSupportActionBar().setBackgroundDrawable(new ColorDrawable(getResources().getColor(R.color.grey)));
    }
    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        MenuInflater inflater = getMenuInflater();
        inflater.inflate(R.menu.mymenus,menu);
        return true;
    }
    @Override
    public boolean onOptionsItemSelected(@NonNull MenuItem item) {
        if (item.getItemId() == R.id.setting) {
            Toast.makeText(this, "Option Settings Clicked", Toast.LENGTH_SHORT).show();
            return true;
        }
        if (item.getItemId() == id.Cmail) {
            Toast.makeText(this, "Option Compose Mail Clicked", Toast.LENGTH_SHORT).show();
            return true;
        }
        if (item.getItemId() == id.feedback){
            Toast.makeText(this, "Option Feedback Clicked", Toast.LENGTH_SHORT).show();
        }
        if (item.getItemId() == id.search){
            Toast.makeText(this, "Option Search clicked", Toast.LENGTH_SHORT).show();
        }
        return super.onOptionsItemSelected(item);
    }
}
				mymenus.xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:id="@+id/search" android:title="Search"></item>
    <item android:id="@+id/Cmail" android:title="Compose Mail" android:enabled="false"></item>
    <item android:id="@+id/feedback" android:title="Feedback"></item>
    <item android:id="@+id/setting" android:title="Settings"></item>
</menu>


			activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingVertical="40sp"
        android:text="Practical 6"
        android:textColor="@color/black"
        android:textSize="30sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.099" />

</androidx.constraintlayout.widget.ConstraintLayout>




