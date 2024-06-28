<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>kagelås</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }
        .container {
            width: 80%;
            margin: 0 auto;
            overflow: hidden;
        }
        header {
            background: #333;
            color: #fff;
            padding-top: 30px;
            min-height: 70px;
            border-bottom: #77aaff 3px solid;
        }
        header a {
            color: #fff;
            text-decoration: none;
            text-transform: uppercase;
            font-size: 16px;
        }
        header ul {
            padding: 0;
            list-style: none;
        }
        header li {
            display: inline;
            padding: 0 20px 0 20px;
        }
        .showcase {
            min-height: 400px;
            background: url('your-image.jpg') no-repeat 0 -400px;
            text-align: center;
            color: #fff;
        }
        .showcase h1 {
            margin-top: 100px;
            font-size: 55px;
            margin-bottom: 10px;
        }
        .showcase p {
            font-size: 20px;
        }
        .product {
            padding: 20px;
            background: #fff;
            margin-top: 20px;
            border-radius: 5px;
        }
        .product img {
            max-width: 100%;
        }
        .product h2 {
            margin-top: 0;
        }
        .payment-info, .contact-info {
            margin-top: 20px;
            padding: 20px;
            background: #fff;
            border-radius: 5px;
        }
        footer {
            background: #333;
            color: #fff;
            text-align: center;
            padding: 10px 0;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>kagelås</h1>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Store</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </div>
    </header>
    <section class="showcase">
        <div class="container">
            <h1>Welcome to kagelås</h1>
            <p>Your solution for secure and invisible locks</p>
        </div>
    </section>
    <div class="container">
        <section class="product">
            <h2>The stasher™ lock</h2>
            <img src="your-product-image.jpg" alt="The stasher™ lock">
            <p>The stasher lock is an invisible lock that guarantees complete privacy without the need of buying a safe. It easily converts any drawer into a safe. The lock isn't just safe and secure, it's also really strong and really hard to break.</p>
            <p><strong>Price:</strong> $25.95</p>
            <h3>Payment Details</h3>
            <div id="paypal-button-container"></div>
            <p>Please use PayPal to complete your payment and send the confirmation to our contact below.</p>
        </section>
        <section class="contact-info">
            <h3>Contact Information</h3>
            <p><strong>WhatsApp:</strong> +92 3167546410</p>
        </section>
    </div>
    <footer>
        <p>kagelås &copy; 2024</p>
    </footer>
    <script src="https://www.paypal.com/sdk/js?client-id=YOUR_PAYPAL_CLIENT_ID"></script>
    <script>
        paypal.Buttons({
            createOrder: function(data, actions) {
                return actions.order.create({
                    purchase_units: [{
                        amount: {
                            value: '25.95'
                        }
                    }]
                });
            },
            onApprove: function(data, actions) {
                return actions.order.capture().then(function(details) {
                    alert('Transaction completed by ' + details.payer.name.given_name);
                });
            }
        }).render('#paypal-button-container');
    </script>
</body>
</html>
