## Shared Preferences

### Java

````
// Storing data into SharedPreferences
SharedPreferences sharedPreferences = getSharedPreferences("MySharedPref",MODE_PRIVATE);

// Creating an Editor object to edit(write to the file)
SharedPreferences.Editor editor = sharedPreferences.edit();

// Storing the key and its value as the data fetched from edittext
editor.putString("key", "value");

// Once the changes have been made, we need to commit to apply those changes made, 
// otherwise, it will throw an error
editor.commit();
````

### Kotlin

````
// Storing data into SharedPreferences
val sharedPreferences = getSharedPreferences("MySharedPref", MODE_PRIVATE)
        
// Creating an Editor object to edit(write to the file)
val editor = sharedPreferences.edit()
        
// Storing the key and its value as the data fetched from edittext
editor.putString("key", "value")
        
// Once the changes have been made, we need to commit to apply those changes made, 
// otherwise, it will throw an error
editor.apply()
````
