### To check username and password is Correct 
````
    var username by remember { mutableStateOf(TextFieldValue()) }
    var password by remember { mutableStateOf(TextFieldValue()) }

 if (isValidLogin(username.text, password.text)) {
  onLoginSuccess()
  if (isValidLogin("9164949099", "kiosk123")) {
// Go to Second Activity 
   mContext.startActivity(Intent(mContext,MainActivity::class.java))
         }
    } else {
// Show a message
        Toast.makeText(mContext, R.string.invalid_credentials, Toast.LENGTH_SHORT).show()
      }

fun isValidLogin(username: String, password: String): Boolean {

    return username == "9164949099" && password == "kiosk123"
}
