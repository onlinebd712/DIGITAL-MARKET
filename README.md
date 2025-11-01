<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>পেমেন্ট সিস্টেম</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            text-align: center;
        }
        .container {
            max-width: 400px;
            margin: 0 auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 8px;
            background-color: #f9f9f9;
        }
        h2 {
            color: #333;
            margin-bottom: 20px;
        }
        .payment-options {
            text-align: left;
            margin-bottom: 20px;
        }
        .payment-options label {
            display: block;
            margin-bottom: 10px;
            cursor: pointer;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            background-color: #fff;
        }
        .payment-options input[type="radio"] {
            margin-right: 10px;
        }
        .note {
            background-color: #fff3cd;
            color: #856404;
            padding: 15px;
            border: 1px solid #ffeeba;
            border-radius: 5px;
            margin-top: 20px;
            text-align: justify;
        }
        .button {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        .button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>

<div class="container">
    <h2>পেমেন্ট সিস্টেম</h2>
    
    <form action="/process_payment" method="post">
        
        <p>কিলিক দিলে যেন৷ এই অপশন আসে:</p>
        
        <div class="payment-options">
            <label>
                <input type="radio" name="payment_method" value="bKash" required>
                বিকাশ
            </label>
            <label>
                <input type="radio" name="payment_method" value="Nagad" required>
                নগদ
            </label>
            <label>
                <input type="radio" name="payment_method" value="Rocket" required>
                রকেট
            </label>
        </div>
        
        <div class="note">
            <p><strong>গুরুত্বপূর্ণ নোট:</strong></p>
            <p>পেমেন্ট রিকুয়েস্ট দিতে হলে আপনার একাউন্টে ৬৭০ টাকা বেশি থাকতে হবে।</p>
        </div>
        
        <br>
        
        <button type="submit" class="button">পেমেন্ট করুন</button>
        
    </form>
</div>

</body>
</html>
