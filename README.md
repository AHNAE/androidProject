//activity_mail.xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.drawerlayout.widget.DrawerLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/drawer_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#000000"
    android:fitsSystemWindows="true"
    tools:openDrawer="start">

    <include layout="@layout/app_bar_main"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

    <com.google.android.material.navigation.NavigationView
        android:id="@+id/nav_view"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:layout_gravity="start"
        android:fitsSystemWindows="true"
        android:background="#000000"
        app:itemTextColor="#ffffff"
        app:headerLayout="@layout/nav_header_main"
        app:menu="@menu/activity_main_drawer" />
</androidx.drawerlayout.widget.DrawerLayout>

//activity_main_drawer.xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    tools:showIn="navigation_view">

    <group android:checkableBehavior="single">
        <item
            android:id="@+id/nav_battle"
            android:title="다이어트 대결"/>
        <item
            android:id="@+id/nav_calculator"
            android:title="칼로리 계산기"/>
        <item
            android:id="@+id/nav_board"
            android:title="게시판"/>
    </group>

    <group android:checkableBehavior="single">
        <item
            android:id="@+id/nav_logout"
            android:title="로그아웃"/>
        <item
            android:id="@+id/nav_notice"
            android:title="공지사항"/>
        <item
            android:id="@+id/nav_cs"
            android:title="고객센터"/>
    </group>
</menu>

//content_main.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:background="#000000"
    app:layout_behavior="@string/appbar_scrolling_view_behavior"
    tools:showIn="@layout/app_bar_main">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:background="#ffffff">

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:paddingTop="20dp"
            android:src="@drawable/navlogo"/>

        <TextView
            android:id="@+id/tvUserID"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:text="닉네임"
            android:textSize="17dp"
            android:textColor="#000000"
            android:fontFamily="@font/dalmoorifont"
            android:layout_margin="20dp"/>

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:gravity="center">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:paddingTop="5dp"
                android:text="Lv."
                android:textSize="20dp"
                android:textColor="#000000"
                android:fontFamily="@font/dalmoorifont"
                android:gravity="right"/>

            <RatingBar
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:numStars="4"
                android:isIndicator="true"
                android:rating="0.5"
                android:stepSize="0.5"
                style="?android:attr/ratingBarStyleIndicator"/>
        </LinearLayout>

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:paddingTop="20dp">

            <Button
                android:id="@+id/btnUserDaily"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:text="출석"
                android:background="@drawable/buttoncustom2"
                android:textColor="#ffffff"
                android:fontFamily="@font/dalmoorifont"/>

            <Button
                android:id="@+id/btnUserMission"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:text="미션"
                android:background="@drawable/buttoncustom2"
                android:textColor="#ffffff"
                android:fontFamily="@font/dalmoorifont"/>

            <Button
                android:id="@+id/btnUserInfo"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:text="내 정보"
                android:background="@drawable/buttoncustom2"
                android:textColor="#ffffff"
                android:fontFamily="@font/dalmoorifont"/>
        </LinearLayout>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical"
        android:layout_weight="1">

        <FrameLayout
            android:id="@+id/frame_main"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toTopOf="parent"/>

        <fragment
            android:id="@+id/nav_host_fragment"
            android:name="androidx.navigation.fragment.NavHostFragment"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            app:defaultNavHost="true"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toTopOf="parent"
            app:navGraph="@navigation/mobile_navigation" />

    </LinearLayout>
</LinearLayout>

//appbar_main.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="280dp"
    android:layout_height="match_parent"
    android:layout_gravity="start"
    android:id="@+id/drawerView"
    android:background="#000000">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="horizontal"
        android:background="#000000">

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:src="@drawable/navlogo"
            android:id="@+id/main_icon"
            android:layout_centerHorizontal="true"
            android:layout_marginTop="40dp">
        </ImageView>

        <TextView
            android:id="@+id/NavTvUserID"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="닉네임"
            android:textSize="15dp"
            android:layout_marginTop="30dp"
            android:layout_centerHorizontal="true"
            android:fontFamily="@font/dalmoorifont"
            android:textColor="#ffffff"
            android:layout_below="@id/main_icon">
        </TextView>

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:gravity="center"
            android:layout_marginTop="10dp"
            android:layout_below="@+id/NavTvUserID">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:paddingTop="5dp"
                android:text="Lv."
                android:textSize="20dp"
                android:textColor="#ffffff"
                android:fontFamily="@font/dalmoorifont"
                android:gravity="right"/>

            <RatingBar
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:numStars="4"
                android:isIndicator="true"
                android:rating="0.5"
                android:stepSize="0.5"
                style="?android:attr/ratingBarStyleIndicator"/>
        </LinearLayout>

        <TextView
            android:id="@+id/nav_dietbattle"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:text="다이어트 대결"
            android:fontFamily="@font/dalmoorifont"
            android:textColor="#ffffff"
            android:layout_marginTop="245dp"
            android:layout_marginLeft="44dp"
            android:padding="20dp"
            android:layout_centerHorizontal="true"
            android:background="@drawable/buttoncustom"
            android:onClick="OnClick">
        </TextView>

        <TextView
            android:id="@+id/nav_calculator"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:text="칼로리 계산기"
            android:fontFamily="@font/dalmoorifont"
            android:textColor="#ffffff"
            android:layout_marginTop="345dp"
            android:layout_marginLeft="44dp"
            android:padding="20dp"
            android:layout_centerHorizontal="true"
            android:background="@drawable/buttoncustom"
            android:onClick="OnClick">
        </TextView>

        <TextView
            android:id="@+id/nav_board"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:text="게시판"
            android:fontFamily="@font/dalmoorifont"
            android:textColor="#ffffff"
            android:layout_marginTop="445dp"
            android:layout_marginLeft="44dp"
            android:padding="20dp"
            android:layout_centerHorizontal="true"
            android:background="@drawable/buttoncustom"
            android:onClick="OnClick">
        </TextView>

        <TextView
            android:id="@+id/nav_logout"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginLeft="35dp"
            android:text="로그아웃"
            android:fontFamily="@font/dalmoorifont"
            android:textSize="15dp"
            android:textColor="#ffffff"
            android:layout_marginTop="550dp"
            android:layout_alignParentLeft="true"
            android:onClick="OnClick">
        </TextView>

        <TextView
            android:id="@+id/nav_notice"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginLeft="35dp"
            android:text="공지사항"
            android:fontFamily="@font/dalmoorifont"
            android:textSize="15dp"
            android:textColor="#ffffff"
            android:layout_marginTop="600dp"
            android:layout_alignParentLeft="true"
            android:onClick="OnClick">
        </TextView>

        <TextView
            android:id="@+id/nav_cs"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginLeft="35dp"
            android:text="고객센터"
            android:fontFamily="@font/dalmoorifont"
            android:textSize="15dp"
            android:textColor="#ffffff"
            android:layout_marginTop="650dp"
            android:layout_alignParentLeft="true"
            android:onClick="OnClick">
        </TextView>
    </RelativeLayout>

</LinearLayout>

//mainActivity.java
package com.example.funnyeasybattleex;

import android.os.Build;
import android.os.Bundle;
import android.view.View;
import android.view.Menu;
import android.widget.Button;

import com.google.android.material.appbar.AppBarLayout;
import com.google.android.material.floatingactionbutton.FloatingActionButton;
import com.google.android.material.snackbar.Snackbar;
import com.google.android.material.navigation.NavigationView;

import androidx.annotation.NonNull;
import androidx.appcompat.app.ActionBar;
import androidx.fragment.app.FragmentManager;
import androidx.fragment.app.FragmentTransaction;
import androidx.navigation.NavController;
import androidx.navigation.Navigation;
import androidx.navigation.ui.AppBarConfiguration;
import androidx.navigation.ui.NavigationUI;
import androidx.drawerlayout.widget.DrawerLayout;
import androidx.appcompat.app.AppCompatActivity;
import androidx.appcompat.widget.Toolbar;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {

    Button btnUserDaily, btnUserMission, btnUserInfo;
    FragmentManager fm;
    FragmentTransaction tran;
    Frag_daily frag1;
    Frag_mission frag2;
    Frag_user frag3;

    private AppBarConfiguration mAppBarConfiguration;
    private DrawerLayout drawerLayout;
    private View drawerView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Toolbar toolbar = (Toolbar) findViewById(R.id.toolbar);
        setSupportActionBar(toolbar);
        DrawerLayout drawer = findViewById(R.id.drawer_layout);
        // Passing each menu ID as a set of Ids because each
        // menu should be considered as top level destinations.
        mAppBarConfiguration = new AppBarConfiguration.Builder(
                R.id.nav_home, R.id.nav_gallery, R.id.nav_slideshow)
                .setDrawerLayout(drawer)
                .build();
        NavigationView navigationView = findViewById(R.id.nav_view);
        NavController navController = Navigation.findNavController(this, R.id.nav_host_fragment);
        NavigationUI.setupActionBarWithNavController(this, navController, mAppBarConfiguration);
        NavigationUI.setupWithNavController(navigationView, navController);
        btnUserDaily = (Button) findViewById(R.id.btnUserDaily);
        btnUserMission = (Button) findViewById(R.id.btnUserMission);
        btnUserInfo = (Button) findViewById(R.id.btnUserInfo);
        btnUserDaily.setOnClickListener(this);
        btnUserMission.setOnClickListener(this);
        btnUserInfo.setOnClickListener(this);
        frag1 = new Frag_daily();
        frag2 = new Frag_mission();
        frag3 = new Frag_user();

        fm = getSupportFragmentManager();
        tran = fm.beginTransaction();
        tran.replace(R.id.frame_main, frag1).commitAllowingStateLoss();
    }

    @Override
    public boolean onSupportNavigateUp() {
        NavController navController = Navigation.findNavController(this, R.id.nav_host_fragment);
        return NavigationUI.navigateUp(navController, mAppBarConfiguration)
                || super.onSupportNavigateUp();
    }

    @Override
    public void onClick(View view) {
        tran = fm.beginTransaction();
        switch (view.getId()) {
            case R.id.btnUserDaily:
                tran.replace(R.id.frame_main, frag1).commitAllowingStateLoss();
                break;
            case R.id.btnUserMission:
                tran.replace(R.id.frame_main, frag2).commitAllowingStateLoss();
                break;
            case R.id.btnUserInfo:
                tran.replace(R.id.frame_main, frag3).commitAllowingStateLoss();
                break;
        }
    }
}

//manifest.xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.funnyeasybattleex">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity
            android:name=".SplashActivity"
            android:theme="@style/SplashTheme">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".MainActivity"
            android:theme="@style/AppTheme.NoActionBar"/>
    </application>

</manifest>

//
