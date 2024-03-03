# Create Custom Instruction Dialog


### XML DESIGN

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical"
    >

    <ImageView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:src="@drawable/android"
        android:layout_gravity="center"
        />

    <ImageView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:src="@drawable/home"
        android:layout_gravity="center"
        android:layout_marginTop="30dp"
        />

    <ImageView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:src="@drawable/pic"
        android:layout_marginTop="30dp"
        android:layout_gravity="center"
        />

</LinearLayout>
```

### Create XML Layout
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp"
    android:gravity="center_horizontal"
    >

    <View
        android:layout_width="105dp"
        android:layout_height="105dp"
        android:id="@+id/view1"
        android:background="@drawable/outline"
        />

    <View
        android:layout_width="105dp"
        android:layout_height="105dp"
        android:id="@+id/view2"
        android:layout_marginTop="10dp"
        android:background="@drawable/outline"
        />

    <View
        android:layout_width="105dp"
        android:layout_height="105dp"
        android:id="@+id/view3"
        android:layout_marginTop="10dp"
        android:background="@drawable/outline"
        />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/text_view"
        android:textSize="18sp"
        android:textColor="@color/white"
        android:layout_marginTop="32dp"
        />

</LinearLayout>
```

### Create Drawable File
```
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android" android:shape="rectangle">

    <stroke android:color="@android:color/holo_blue_light" android:width="1dp"/>
    <corners android:radius="30dp"/>

</shape>
```

### JAVA

create method
```
displayDialog();
```

```
  private void displayDialog() {
        // Initialize dialog
        Dialog dialog = new Dialog(this);

        // Set View
        dialog.setContentView(R.layout.dialog_ins);

        // Set layout
        dialog.getWindow().setLayout(WindowManager.LayoutParams.MATCH_PARENT, WindowManager.LayoutParams.MATCH_PARENT);

        // Set Background
        dialog.getWindow().setBackgroundDrawable(new ColorDrawable(Color.TRANSPARENT));

        // Show dialog
        dialog.show();

        // Initialize and assign variable
        View view1 = dialog.findViewById(R.id.view1);
        View view2 = dialog.findViewById(R.id.view2);
        View view3 = dialog.findViewById(R.id.view3);
        TextView text_view = dialog.findViewById(R.id.text_view);

        // Set Text for button instruction
        text_view.setText("This is First Image");

        view1.setOnClickListener(view -> {

            view1.setVisibility(View.INVISIBLE);
            view2.setVisibility(View.VISIBLE);
            text_view.setText("This is Second Image");
        });

        view2.setOnClickListener(view -> {

            view2.setVisibility(View.INVISIBLE);
            view3.setVisibility(View.VISIBLE);
            text_view.setText("This is Third Image");
        });

        view3.setOnClickListener(view -> {
            dialog.dismiss();
        });
```

### Result
<img src="https://i.ibb.co/Mcgmz9g/screenshot-1709475891544.png"/>

