### Broadcast & Receiver
#### fist add to AndroidManifest
````
 <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>
````
````
</activity>
..... 
  <receiver android:name=".BootReceiver"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.BOOT_COMPLETED"/>
            </intent-filter>
        </receiver>
.....
</application>
````
#### create class 
````
class BootReceiver : BroadcastReceiver() {
    override fun onReceive(context: Context?, intent: Intent?) {

        if (intent?.action == Intent.ACTION_BOOT_COMPLETED) {
            
            Toast.makeText(context, "Welcome back", Toast.LENGTH_LONG).show()
        }
    }
}
````
