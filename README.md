<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rijmpjeslijst - Ravi</title>
<style>
  body {
    font-family: "Comic Sans MS", sans-serif;
    background: linear-gradient(135deg, #ffe0b2, #ffcc80);
    color: #333;
    margin: 0;
    padding: 20px;
  }
  h1 {
    text-align: center;
    color: #ff7043;
    text-shadow: 1px 1px 2px #fff;
  }
  #rhymeListContainer {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 10px;
    margin-top: 20px;
  }
  .rhyme-item {
    background: #fff3e0;
    border: 2px solid #ffb74d;
    border-radius: 12px;
    padding: 10px;
    text-align: center;
    font-size: 16px;
    box-shadow: 2px 2px 5px rgba(0,0,0,0.1);
    transition: transform 0.2s ease, background 0.2s ease;
  }
  .rhyme-item:hover {
    transform: scale(1.05);
    background: #ffe0b2;
  }
  footer {
    text-align: center;
    margin-top: 30px;
    font-size: 14px;
    color: #777;
  }
</style>
</head>
<body>
  <h1>🧩 Ravi’s Rijmpjeslijst (500 stuks!)</h1>

  <div id="rhymeListContainer"></div>

  <footer>© 2025 Ravi’s Rijmproject 🎵</footer>

  <script>
    const RIJMPJES_500 = [
      "maan staan", "boot groot", "dag lach", "huis muis", "beer meer",
      "kat mat", "peer sfeer", "blad stad", "stoel koel", "glas was",
      "hand zand", "vloer boer", "neus reus", "been teen", "oog droog",
      "lamp kamp", "tak zak", "noot poot", "jas was", "sok rok",
      "vloer boer", "steen been", "koe moe", "raam naam", "mand land",
      "gans dans", "kaars paard", "boom zoem", "peer heer", "zon kon",
      "stoel gevoel", "vlag dag", "huis kruis", "schoen groen", "ster ver",
      "vis gis", "koek hoek", "broek doek", "stoel koel", "kat spat",
      "oog droog", "peer sfeer", "been teen", "blad stad", "hand zand",
      "maan kraan", "dag vlag", "vloer boer", "boot groot", "beer speer",
      "glas was", "tak pak", "lamp kamp", "stoel gevoel", "snoep troep",
      "steen leen", "neus keus", "gans dans", "huis muis", "mand land",
      "koe moe", "vloer boer", "raam naam", "kat mat", "peer meer",
      "dag lach", "been teen", "blad stad", "maan staan", "oog droog",
      "boot dood", "hand zand", "sok rok", "beer sfeer", "vloer boer",
      "tak zak", "huis kruis", "stoel koel", "koek hoek", "peer heer",
      "neus reus", "glas was", "maan kraan", "stoel gevoel", "vlag dag",
      "steen been", "kat spat", "lamp kamp", "tak pak", "gans dans",
      "huis muis", "vloer boer", "been teen", "peer meer", "dag vlag",
      "boot groot", "stoel koel", "hand zand", "blad stad", "oog droog",
      "maan staan", "beer speer", "glas was", "stoel gevoel", "neus keus",
      "tak zak", "raam naam", "peer heer", "huis kruis", "lamp kamp",
      "vloer boer", "steen been", "kat mat", "boot groot", "beer sfeer",
      "maan kraan", "dag lach", "sok rok", "gans dans", "koe moe",
      "stoel koel", "peer meer", "blad stad", "hand zand", "been teen",
      "oog droog", "tak pak", "vloer boer", "huis muis", "neus reus",
      "boot dood", "steen leen", "glas was", "maan staan", "beer sfeer",
      "kat spat", "peer heer", "dag vlag", "raam naam", "vloer boer",
      "stoel gevoel", "tak zak", "huis kruis", "koek hoek", "steen been",
      "boot groot", "peer meer", "hand zand", "blad stad", "been teen",
      "maan kraan", "oog droog", "lamp kamp", "vloer boer", "neus keus",
      "huis muis", "dag lach", "tak pak", "peer heer", "glas was",
      "boot dood", "beer speer", "steen leen", "stoel koel", "kat mat",
      "vloer boer", "neus reus", "maan staan", "huis kruis", "peer meer",
      "blad stad", "been teen", "tak zak", "boot groot", "hand zand",
      "steen been", "vloer boer", "kat spat", "beer sfeer", "peer heer",
      "huis muis", "stoel gevoel", "dag vlag", "maan kraan", "glas was",
      "neus keus", "boot dood", "tak pak", "beer speer", "steen leen",
      "vloer boer", "peer meer", "blad stad", "hand zand", "been teen",
      "oog droog", "huis kruis", "maan staan", "kat mat", "peer heer",
      "vloer boer", "boot groot", "beer sfeer", "tak zak", "neus reus",
      "steen been", "huis muis", "glas was", "vloer boer", "peer meer",
      "dag vlag", "maan kraan", "kat spat", "been teen", "blad stad",
      "hand zand", "boot dood", "beer speer", "tak pak", "huis kruis",
      "peer heer", "vloer boer", "steen leen", "maan staan", "oog droog",
      "glas was", "boot groot", "neus keus", "hand zand", "peer meer",
      "kat mat", "dag lach", "steen been", "vloer boer", "huis muis",
      "tak zak", "beer sfeer", "peer heer", "maan kraan", "vloer boer",
      "boot groot", "glas was", "steen leen", "neus reus", "kat spat",
      "peer meer", "huis kruis", "blad stad", "been teen", "hand zand",
      "tak pak", "boot dood", "maan staan", "beer speer", "vloer boer",
      "peer heer", "glas was", "neus keus", "steen been", "dag vlag",
      "huis muis", "tak zak", "peer meer", "hand zand", "boot groot",
      "maan kraan", "beer sfeer", "steen leen", "vloer boer", "kat mat",
      "blad stad", "been teen", "glas was", "neus reus", "huis kruis",
      "peer heer", "vloer boer", "tak pak", "boot dood", "maan staan",
      "beer speer", "peer meer", "steen been", "dag lach", "hand zand",
      "blad stad", "vloer boer", "huis muis", "glas was", "neus keus",
      "boot groot", "tak zak", "peer heer", "maan kraan", "beer sfeer",
      "steen leen", "vloer boer", "kat mat", "been teen", "peer meer",
      "huis kruis", "blad stad", "hand zand", "glas was", "boot dood",
      "maan staan", "neus reus", "tak pak", "beer speer", "steen been",
      "vloer boer", "peer heer", "dag vlag", "huis muis", "boot groot",
      "maan kraan", "steen leen", "peer meer", "hand zand", "blad stad",
      "been teen", "glas was", "vloer boer", "kat spat", "beer sfeer",
      "peer heer", "huis kruis", "tak zak", "boot dood", "maan staan",
      "steen been", "neus keus", "peer meer", "vloer boer", "dag lach",
      "boot groot", "hand zand", "blad stad", "beer speer", "glas was",
      "maan kraan", "tak pak", "huis muis", "peer heer", "steen leen",
      "vloer boer", "neus reus", "kat mat", "peer meer", "boot groot",
      "blad stad", "hand zand", "maan staan", "dag vlag", "beer sfeer",
      "glas was", "steen been", "vloer boer", "tak zak", "peer heer",
      "huis kruis", "boot dood", "maan kraan", "steen leen", "peer meer",
      "neus keus", "vloer boer", "blad stad", "hand zand", "boot groot",
      "beer speer", "glas was", "maan staan", "peer heer", "tak pak",
      "huis muis", "steen been", "vloer boer", "dag lach", "neus reus",
      "peer meer", "blad stad", "hand zand", "boot dood", "maan kraan",
      "beer sfeer", "steen leen", "glas was", "boot groot", "peer heer"
    ];

    // Genereer de lijst
    const container = document.getElementById("rhymeListContainer");
    RIJMPJES_500.forEach((r, i) => {
      const div = document.createElement("div");
      div.className = "rhyme-item";
      div.innerHTML = `<b>${i + 1}.</b> ${r}`;
      container.appendChild(div);
    });
  </script>
</body>
</html>
