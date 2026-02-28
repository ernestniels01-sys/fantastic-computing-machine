# fantastic-computing-machine
Energy refilling game
<!DOCTYPE html>
<html>
<head>
    <title>Beneath the Surface</title>
    <style>
        body { background: #001a33; color: white; font-family: 'Courier New', monospace; text-align: center; padding: 50px; }
        .box { border: 1px solid #0059b3; padding: 20px; border-radius: 10px; background: rgba(0,0,0,0.5); }
        button { background: #0059b3; color: white; border: none; padding: 10px 20px; cursor: pointer; margin: 10px; }
    </style>
</head>
<body>
    <div class="box">
        <h1>Beneath the Surface</h1>
        <p id="story-text">The water is deep and full of secrets...</p>
        <button onclick="makeChoice('Dive')">Dive In</button>
        <button onclick="makeChoice('Stay')">Stay on Shore</button>
    </div>

    <script>
        async function makeChoice(val) {
            const response = await fetch('/action', {
                method: 'POST',
                headers: {'Content-Type': 'application/json'},
                body: JSON.stringify({choice: val})
            });
            const data = await response.json();
            alert(data.message);
        }
    </script>
</body>
</html>
