### foreground Service
````
class RunningApp : Application() {
    
        // Create a notification channel for running notifications on Android Oreo and above
        override fun onCreate() {
            super.onCreate()
            if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
                val channel = NotificationChannel(
                    "running_channel",
                    "Running Notification",
                    NotificationManager.IMPORTANCE_HIGH
                )
                val notificationManager = getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
                notificationManager.createNotificationChannel(channel)
            }
        }
    }
````
````
class RunningService : Service() {

    // This method is called when the service is bound to an activity
    override fun onBind(intent: Intent?): IBinder? {
        return null
    }

    @RequiresApi(Build.VERSION_CODES.O)
    @SuppressLint("InflateParams")
    // This method is called when the service is started by an activity or other components
    override fun onStartCommand(intent: Intent?, flags: Int, startId: Int): Int {
        start()
        return START_STICKY  // Ensures service is restarted if it gets terminated
    }

    @RequiresApi(Build.VERSION_CODES.O)
    // This method is called to start the service in the foreground with a notification to the user
    private fun start() {
        val notification = NotificationCompat.Builder(this, "running_channel")
            .setSmallIcon(R.drawable.ic_launcher_foreground)
            .setContentTitle("Time")
            .setContentText("Hour")
            .setPriority(NotificationCompat.PRIORITY_HIGH)  // Set priority to match the channel's importance
            .build()
        startForeground(1, notification)
    }
}
````
#### Add permission to manifest
````
<uses-permission android:name="android.permission.FOREGROUND_SERVICE"/>
````
