MMarktplaats.github.io
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mierenmarktplaats</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f6e5c9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            max-width: 320px; /* Aangepast naar 320px */
            padding: 16px; /* Aangepast naar 16px */
            background-color: #fff;
            border-radius: 8px; /* Aangepast naar 8px */
            box-shadow: 0 0 8px rgba(0, 0, 0, 0.2); /* Aangepast naar 8px */
            text-align: center;
        }
        h1 {
            color: #ff704d;
            margin-bottom: 16px; /* Aangepast naar 16px */
            font-size: 22px; /* Aangepast naar 22px */
        }
        p {
            color: #4d4d4d;
            font-size: 12.8px; /* Aangepast naar 12.8px */
            line-height: 1.6;
            margin-bottom: 16px; /* Aangepast naar 16px */
        }
        .form-group {
            margin-bottom: 12.8px; /* Aangepast naar 12.8px */
        }
        .form-label {
            display: block;
            font-weight: bold;
            margin-bottom: 3.2px; /* Aangepast naar 3.2px */
            color: #ff704d;
            font-size: 12.8px; /* Aangepast naar 12.8px */
        }
        .form-control {
            width: 100%;
            padding: 8px; /* Aangepast naar 8px */
            border: 1px solid #e6e6e6;
            border-radius: 4px; /* Aangepast naar 4px */
        }
        .btn {
            display: block;
            width: 100%;
            padding: 16px; /* Aangepast naar 16px */
            background-color: #ff704d;
            color: #fff;
            text-align: center;
            text-decoration: none;
            border-radius: 4px; /* Aangepast naar 4px */
            font-size: 16px; /* Aangepast naar 16px */
            font-weight: bold;
            transition: background-color 0.3s;
        }
        .btn:hover {
            background-color: #ff6347;
        }
        .results-box {
            background-color: #ffedb3;
            padding: 8px; /* Aangepast naar 8px */
            border-radius: 4px; /* Aangepast naar 4px */
            margin-top: 16px; /* Aangepast naar 16px */
            display: none;
        }
        .results-heading {
            color: #ff704d;
            font-size: 16px; /* Aangepast naar 16px */
            font-weight: bold;
            margin-bottom: 8px; /* Aangepast naar 8px */
        }
        .searched-miersoort {
            color: #ff704d;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Welkom bij de Mierenmarkt!</h1>
        <p>Hier vind je deals voor mieren en andere insecten in de categorie "Insecten en Spinnen". De website zoekt de aanbiedingen op Marktplaats, zodat je ze niet zelf hoeft te zoeken.</p>
        <p>Wat zijn mieren? Mieren behoren tot de familie van sociale insecten. Ze leven in kolonies en zijn bekend om hun georganiseerde samenwerking en hiërarchische structuur. Mieren zijn fascinerende wezens die vaak worden gehouden als huisdieren in mierenboerderijen. Het observeren van een mierenkolonie kan een leerzame en boeiende ervaring zijn.</p>
        <p><strong>Let op bij kopen en verkopen:</strong> Het is belangrijk om voorzichtig te zijn bij het kopen en verkopen van mieren. Zorg ervoor dat je te maken hebt met betrouwbare en verantwoordelijke verkopers. Vraag altijd naar de herkomst van de mieren en of ze legaal worden verkocht. Koop geen mieren uit het wild, omdat dit schadelijk kan zijn voor de populatie in de natuur. Als een deal te mooi lijkt om waar te zijn, is het vaak ook zo. Wees kritisch en neem geen risico's met de gezondheid en veiligheid van de mieren.</p>
        <form id="searchForm">
            <div class="form-group">
                <label class="form-label" for="miersoort">Miersoort:</label>
                <input class="form-control" type="text" name="miersoort" id="miersoort" placeholder="Voer de gewenste miersoort in">
            </div>
            <div class="form-group">
                <label class="form-label" for="beginnerMiersoort">Miersoort voor beginners:</label>
                <select class="form-control" name="beginnerMiersoort" id="beginnerMiersoort">
                    <option value="">-- Selecteer een optie --</option>
                    <option value="Lasius Niger">Lasius Niger</option>
                    <option value="Lasius Flavus">Lasius Flavus</option>
                    <option value="Camponotus">Camponotus</option>
                    <option value="Eigen invoer">Eigen invoer</option>
                </select>
            </div>
            <button type="button" class="btn" onclick="searchDeals()">Bekijk de deals</button>
        </form>
        <div class="results-box" id="results">
            <h2 class="results-heading">Resultaten voor <span class="searched-miersoort" id="searchedMiersoort"></span></h2>
            <!-- Hier komen de zoekresultaten van Marktplaats -->
        </div>
    </div>

    <script>
        function searchDeals() {
            const miersoort = document.getElementById("miersoort").value;
            const beginnerMiersoort = document.getElementById("beginnerMiersoort").value;

            // Kies de miersoort voor beginners als deze is ingevuld en niet 'Eigen invoer', anders gebruik de normale zoekterm
            const zoekterm = (beginnerMiersoort && beginnerMiersoort !== 'Eigen invoer') ? beginnerMiersoort : miersoort;

            // URL van Marktplaats met de zoekopdracht parameters
            const url = `https://www.marktplaats.nl/l/dieren-en-toebehoren/insecten-en-spinnen/#q:${zoekterm}`;

            // Open de URL in hetzelfde venster
            window.location.href = url;

            // Toon de resultaten in de website zelf (optioneel)
            document.getElementById("searchedMiersoort").textContent = zoekterm;
            document.getElementById("results").style.display = "block";
        }
    </script>
</body>
</html>
