### Broadcast & Receiver
#### fist add to AndroidManifest
````
 <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/> // We can change the Receiver option
````
````
</activity>
..... 
  <receiver android:name=".BootReceiver"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.BOOT_COMPLETED"/> // We can change the Boot option
            </intent-filter>
        </receiver>
.....
</application>
````
#### create class 
````
class BootReceiver : BroadcastReceiver() {
    override fun onReceive(context: Context?, intent: Intent?) {

// we can add here some code
// for example the phone is restarted show a message  WELCOME BACK

        if (intent?.action == Intent.ACTION_BOOT_COMPLETED) {
            
            Toast.makeText(context, "Welcome back", Toast.LENGTH_LONG).show()
        }
    }
}
````
