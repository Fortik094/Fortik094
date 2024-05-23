<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Реферальная ссылка</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
    }
    .container {
        width: 80%;
        margin: 50px auto;
        text-align: center;
    }
    #referralCounter {
        font-size: 24px;
    }
    #referralLink {
        font-size: 18px;
    }
</style>
</head>
<body>
<div class="container">
    <div id="referralCounter">0</div>
    <div id="referralLink">
        <p>Ваша реферальная ссылка:</p>
        <input type="text" id="referralURL" readonly>
        <button onclick="copyReferralLink()">Копировать ссылку</button>
        <p>+5% к вашему бонусу</p>
    </div>
</div>

<script>
    let referralCounter = 0;

    function copyReferralLink() {
        let copyText = document.getElementById("referralURL");
        copyText.select();
        document.execCommand("copy");
        alert("Ссылка скопирована: " + copyText.value);
    }

    function updateReferralCounter() {
        document.getElementById("referralCounter").innerText = referralCounter;
    }

    function generateReferralLink() {
        let referralLink = "https://t.me/+itlVxzsO96ZkMzNi " + referralCounter;
        document.getElementById("referralURL").value = referralLink;
    }

    window.onload = function() {
        // Проверяем, если в URL есть параметр ref
        const urlParams = new URLSearchParams(window.location.search);
        const refParam = urlParams.get('ref');
        if (refParam !== null) {
            referralCounter = parseInt(refParam);
        }
        updateReferralCounter();
        generateReferralLink();
    };
</script>
</body>
</html>
