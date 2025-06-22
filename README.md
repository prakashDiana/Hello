# Hello
Markdown is <span style="font-family: ui-rounded">cool!</span>
<ins>Hello!</ins>
\*bold?\*
```tex
help\bye ! " \# \$ \% \& ' ( ... \textbackslash ] \^{} \_ ` ... \{ | \} \~{} \- $1+1$ % Help
 4 & 6
\LaTeX
\^a
$2^4$
$2_4$
{help}
\~a
2~6
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3-Letter Word Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
            padding: 20px;
            box-sizing: border-box;
        }

        .game-container {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            text-align: center;
            max-width: 400px;
            width: 100%;
        }

        h1 {
            color: #333;
            margin-bottom: 20px;
        }

        input[type="text"] {
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ddd;
            border-radius: 4px;
            width: calc(100% - 22px);
            margin-bottom: 15px;
            text-transform: uppercase;
        }

        button {
            background-color: #007bff;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #0056b3;
        }

        #message {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            color: #d9534f; /* Red for errors/loss */
        }

        #word-list {
            margin-top: 20px;
            text-align: left;
            border-top: 1px solid #eee;
            padding-top: 15px;
            max-height: 150px;
            overflow-y: auto;
        }

        #word-list h2 {
            font-size: 1.2em;
            color: #555;
            margin-bottom: 10px;
        }

        #word-list ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        #word-list li {
            background-color: #e9ecef;
            margin-bottom: 5px;
            padding: 8px;
            border-radius: 4px;
            color: #333;
        }
    </style>
</head>
<body>
    <div class="game-container">
        <h1>3-Letter Word Game</h1>
        <p>Enter a unique 3-letter word:</p>
        <input type="text" id="wordInput" placeholder="Type your word here" maxlength="3">
        <button onclick="checkWord()">Submit Word</button>
        <div id="message"></div>
        <div id="word-list">
            <h2>Words Used:</h2>
            <ul id="usedWords"></ul>
        </div>
    </div>

    <script>
        let usedWords = [];
        const wordInput = document.getElementById('wordInput');
        const messageDisplay = document.getElementById('message');
        const usedWordsList = document.getElementById('usedWords');

        function checkWord() {
            const word = wordInput.value.trim().toUpperCase(); // Convert to uppercase for case-insensitive check
            messageDisplay.textContent = ''; // Clear previous messages

            if (word.length !== 3) {
                messageDisplay.style.color = '#d9534f';
                messageDisplay.textContent = "That's not a 3-letter word!";
            } else if (usedWords.includes(word)) {
                messageDisplay.style.color = '#d9534f';
                messageDisplay.textContent = "GAME OVER! You lose. Try again.";
                wordInput.disabled = true; // Disable input after game over
            } else {
                usedWords.push(word);
                messageDisplay.style.color = '#5cb85c'; // Green for success
                messageDisplay.textContent = `"${word}" added! Keep going.`;
                updateUsedWordsList();
            }
            wordInput.value = ''; // Clear the input field
            wordInput.focus(); // Keep focus on the input for quick re-entry
        }

        function updateUsedWordsList() {
            usedWordsList.innerHTML = ''; // Clear existing list
            usedWords.forEach(word => {
                const listItem = document.createElement('li');
                listItem.textContent = word;
                usedWordsList.appendChild(listItem);
            });
            // Scroll to the bottom of the list if it overflows
            usedWordsList.scrollTop = usedWordsList.scrollHeight;
        }

        // Allow pressing Enter key to submit
        wordInput.addEventListener('keypress', function(event) {
            if (event.key === 'Enter') {
                checkWord();
            }
        });
    </script>
</body>
</html>
```
# 1
## 2
### 3
#### 4
##### 5
###### 6
Help!
*War**ning*
> [!WARNING]
> help

> [!NOTE]
>  Should get 1 pt each

> [!INFO]
> hellp!!!
