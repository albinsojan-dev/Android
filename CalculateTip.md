### Calculate Tip amount
````
   var amountInput by remember { mutableStateOf("") }

    val amount = amountInput.toDoubleOrNull()?:0.0

    val tip = calculateTip(amount)


private fun calculateTip(amount: Double , tipPercent: Double = 15.0): String {
    val tip = tipPercent / 100 * amount
    return NumberFormat.getCurrencyInstance().format("value")
}

````
