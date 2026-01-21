# JavaScript-Day-7
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Tony's Café Rewards</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #fff3e0;
            padding: 40px;
        }
        .board {
            background: white;
            max-width: 450px;
            margin: auto;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        h2 { text-align: center; }
        p { font-size: 16px; }
        .reward { color: green; font-weight: bold; }
        .alert { color: darkred; font-weight: bold; }
    </style>
</head>
<body>

<div class="board" id="output"></div>

<script>
    // Step 1: Customer Info
    let memberType = "Gold";   // Gold, Silver, Regular
    let totalBill = 950;       // change amount
    let hasCoupon = false;     // true or false
    let isWeekend = false;     // true or false

    let messages = "";

    // Step 2: AND Operator (&&)
    if (memberType === "Gold" && totalBill > 500) {
        messages += "<p class='reward'> You get a free refill and cookie!</p>";
    }

    // Step 3: OR Operator (||)
    if (totalBill > 800 || hasCoupon === true) {
        messages += "<p class='reward'> You qualify for a combo offer!</p>";
    }

    // Step 4: NOT Operator (!)
    if (!isWeekend) {
        messages += "<p class='reward'> Tony’s Café is open!</p>";
    } else {
        messages += "<p class='alert'> Closed for maintenance!</p>";
    }

    // Step 5: Comparison Practice
    if (totalBill >= 1000) {
        messages += "<p class='reward'> You earned a bonus gift!</p>";
    }

    // Display on Digital Board
    document.getElementById("output").innerHTML = `
        <h2> Tony’s Café Reward Board</h2>
        <p><b>Member Type:</b> ${memberType}</p>
        <p><b>Total Bill:</b> ₹${totalBill}</p>
        <p><b>Has Coupon:</b> ${hasCoupon}</p>
        <p><b>Weekend:</b> ${isWeekend}</p>
        <hr>
        ${messages || "<p>No rewards this time </p>"}
    `;
</script>

</body>
</html>
