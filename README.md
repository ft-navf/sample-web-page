<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Music Recommender</title>
   <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #1db954, #191414);
      color: white;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }

    h1 {
      margin-bottom: 20px;
    }

    .container {
      background: rgba(0, 0, 0, 0.6);
      padding: 30px;
      border-radius: 10px;
      width: 90%;
      max-width: 400px;
      text-align: center;
    }

    select, button {
      padding: 10px;
      font-size: 16px;
      margin-top: 10px;
      width: 100%;
      margin-bottom: 20px;
    }

    button {
      background-color: #1db954;
      color: white;
      border: none;
      cursor: pointer;
    }

    button:hover {
      background-color: #17a84d;
    }

    ul {
      list-style-type: none;
      padding: 0;
    }

    li {
      margin-bottom: 10px;
      background: #333;
      padding: 10px;
      border-radius: 5px;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>🎧 Music Recommender</h1>
    <label for="mood">Choose your mood:</label>
    <select id="mood">
      <option value="happy">Happy</option>
      <option value="sad">Sad</option>
      <option value="chill">Chill</option>
      <option value="workout">Workout</option>
    </select>
    <button onclick="getRecommendations()">Get Recommendations</button>
    <ul id="recommendationList"></ul>
  </div>

  <script>
    const musicDB = {
      happy: [
        "Pharrell Williams – Happy",
        "Katy Perry – Firework",
        "Justin Timberlake – Can't Stop the Feeling",
        "BTS – Dynamite"
      ],
      sad: [
        "Adele – Someone Like You",
        "Billie Eilish – Everything I Wanted",
        "Lewis Capaldi – Someone You Loved",
        "Coldplay – The Scientist"
      ],
      chill: [
        "Lauv – Paris in the Rain",
        "Joji – Glimpse of Us",
        "Norah Jones – Sunrise",
        "Bon Iver – Holocene"
      ],
      workout: [
        "Eminem – Lose Yourself",
        "Survivor – Eye of the Tiger",
        "Kanye West – Stronger",
        "Linkin Park – Numb"
      ]
    };

    function getRecommendations() {
      const mood = document.getElementById("mood").value;
      const list = document.getElementById("recommendationList");

      list.innerHTML = "";
      const recommendations = musicDB[mood];

      recommendations.forEach(track => {
        const li = document.createElement("li");
        li.textContent = track;
        list.appendChild(li);
      });
    }
  </script>

</body>
</html>
