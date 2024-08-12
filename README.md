<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Special Message</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(to bottom, #ffccd5, #ffb3e6);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            height: 100%;
            text-align: center;
        }

        .message {
            background: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        input, textarea {
            padding: 10px;
            border: 2px solid #f3a3b1;
            border-radius: 5px;
            margin: 10px 0;
            width: calc(100% - 22px);
            box-sizing: border-box;
        }

        button {
            padding: 10px 20px;
            background-color: #ff6f61;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #ff3d2e;
        }

        /* Hidden music player */
        audio {
            display: none;
        }

        /* Styling for iframe */
        iframe {
            width: 100%;
            height: 240px;
            border: none;
            border-radius: 10px;
        }

        /* Unique font style for name input */
        .name-section {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            color: #ff3366;
            font-size: 24px;
            font-weight: bold;
        }

        .name-input {
            border: 2px solid #ff3366;
        }

        .highlight {
            font-size: 18px;
            font-weight: bold;
            color: #ff3366;
        }

        .instructions {
            text-align: left;
            margin: 20px auto;
            max-width: 400px;
        }
    </style>
</head>
<body>
    <audio id="backgroundMusic" src="https://example.com/your-audio-file.mp3" autoplay loop></audio>

    <div class="container">
        <div class="message">
            <h1 class="name-section">Hey there!</h1>
            <p class="name-section">What's your name?</p>
            <input type="text" id="name" class="name-input" placeholder="Your Name">
            <button onclick="submitName()">Submit</button>
        </div>
    </div>

    <script>
        function submitName() {
            const name = document.getElementById('name').value;
            if (name) {
                document.body.innerHTML = `
                    <div class="container">
                        <div class="message">
                            <h1>❤️ Hello ${name}! ❤️</h1>
                            <p>Did someone kidnap you?</p>
                            <button disabled>Yes</button>
                            <button onclick="handleResponse()">No</button>
                        </div>
                    </div>
                `;
            }
        }

        function handleResponse() {
            document.body.innerHTML = `
                <div class="container">
                    <div class="message">
                        <h1>Oh no! Why were you so inactive?</h1>
                        <textarea id="reason" placeholder="Your Reason"></textarea>
                        <button onclick="submitReason()">Submit</button>
                    </div>
                </div>
            `;
        }

        function submitReason() {
            document.body.innerHTML = `
                <div class="container">
                    <div class="message">
                        <h1>Too much texting can be dull!</h1>
                        <p>Our time together is fantastic, and I really value our vibe. How about a spicy momo date?</p>
                        <button onclick="scheduleDate()">Yes</button>
                        <button onclick="noDate()">No</button>
                    </div>
                </div>
            `;
        }

        function scheduleDate() {
            document.body.innerHTML = `
                <div class="container">
                    <div class="message">
                        <h1>Select a date and time for our spicy momo date!</h1>
                        <input type="date" id="date">
                        <input type="time" id="time">
                        <button onclick="confirmDate()">Confirm</button>
                    </div>
                </div>
            `;
        }

        function confirmDate() {
            document.body.innerHTML = `
                <div class="container">
                    <div class="message">
                        <h1>Thanks for choosing a date!</h1>
                        <iframe width="560" height="315" src="https://www.youtube.com/embed/t4Diiy_dhkw?si=AKKyERnIMEBGQarJ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                        <div class="instructions">
                            <h2 class="highlight">To text me on WhatsApp:</h2>
                            <ul>
                                <li>Open WhatsApp.</li>
                                <li>Search for <span class="highlight">Cherry 🍒</span>.</li>
                                <li>Send a message saying "Hey".</li>
                            </ul>
                        </div>
                    </div>
                </div>
            `;
        }

        function noDate() {
            document.body.innerHTML = `
                <div class="container">
                    <div class="message">
                        <h1>Okay, maybe next time!</h1>
                    </div>
                </div>
            `;
        }
    </script>
</body>
</html>
