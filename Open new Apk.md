## Open another Apk from an activity 

### Step 1 - Copy the below code to Android Manifest file
````
  <queries>
        <package android:name="com.airbus.agnet.work.production" />
    </queries>
````

### Step 2 - Copy the below code to Activity 
````
 val i = packageManager.getLaunchIntentForPackage("com.airbus.agnet.work.production")
 startActivity(i)
````
