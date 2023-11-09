## Splash Screen

### Kotlin

````
Handler().postDelayed({

            val intent = Intent(this, MainActivity::class.java)
            startActivity(intent)
            finish()

}, 3000)
````

### Java

````
new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                
                Intent intent = new Intent(this, MainActivity.class);
                startActivity(intent);
                finish();
            }
        }, 3000);
````
