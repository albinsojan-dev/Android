### Calculate Tip amount

/**
 * Calculates the tip based on the user input and format the tip amount
 * according to the local currency.
 * Example would be "$10.00".
 */
````
   var amountInput by remember { mutableStateOf("") }

    val amount = amountInput.toDoubleOrNull()?:0.0

    val tip = calculateTip(amount)


private fun calculateTip(amount: Double , tipPercent: Double = 15.0): String {
    val tip = tipPercent / 100 * amount
    return NumberFormat.getCurrencyInstance().format("value")
}

````

### Update the calculateTip() function to round the tip

````
var roundUp by remember { mutableStateOf(false) }

val tip = calculateTip(amount,TipPercent,roundUp)


private fun calculateTip(
    amount:Double,
    tipPercent: Double = 15.0,
    roundUp: Boolean
):String{

    var tip = tipPercent / 100 * amount

    if (roundUp){
        tip = kotlin.math.ceil(tip)
    }
    return NumberFormat.getCurrencyInstance().format(tip)
}




