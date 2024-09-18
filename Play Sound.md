### Sound Play 
````
class PlaySound {
    // Function to create and play a sound based on a resource ID
     fun playSound(context: Context, soundResource: Int) {
         // Retrieve shared preferences
        val sharedPreferences = context.getSharedPreferences("MyPrefs", MODE_PRIVATE)
        val playSound = sharedPreferences.getBoolean("play_wifi", false)
        if (playSound) {
            val manager = context.getSystemService(Context.AUDIO_SERVICE) as AudioManager
            manager.setStreamVolume(AudioManager.STREAM_MUSIC,100 , 0)
            // Get the default notification sound URI
//             val notification = RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION)
            val player: MediaPlayer = MediaPlayer.create(context, soundResource)
            // Check if the device is not in silent mode
            if(manager.ringerMode != AudioManager.RINGER_MODE_SILENT)
                // Start playing the sound
                player.start()
        }
    }
}
````
#### call the function 
  ````
  PlaySound().playSound(context, R.raw.yourdevicedisconnectedfromwifi)
  ````