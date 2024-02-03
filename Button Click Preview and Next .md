### Button click preview and next show image 

````
@Composable
fun ShowImage(modifier: Modifier = Modifier) {

    val images = listOf(
        R.drawable.image1,
        R.drawable.image2,
        R.drawable.image3,
        // Add more image resource IDs as needed
    )

    var currentIndex by remember { mutableStateOf(0) }

    Column(

    ) {
        Image(
            painter = painterResource(id = images[currentIndex]),
            contentDescription = null,
        )
        // Buttons Row
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .padding(16.dp),
            horizontalArrangement = Arrangement.SpaceBetween
        ) {

            // Preview Button
            Button(
                onClick = {
                    // Handle Preview button click
                    currentIndex = (currentIndex - 1).coerceIn(0, images.size - 1)
                }
            ) {
                Text(text = stringResource(R.string.preview))
            }

            // Next Button
            Button(
                onClick = {
                    // Handle Next button click

                    currentIndex = (currentIndex + 1).coerceIn(0, images.size - 1)
                }
            ) {
                Text(text = stringResource(R.string.next))
            }
        }
    }
}
