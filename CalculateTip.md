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
