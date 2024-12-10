<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculateur de Mention</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(to right, #4facfe, #00f2fe);
            color: #333;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background: #ffffff;
            border-radius: 10px;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.1);
            padding: 20px 40px;
            max-width: 400px;
            text-align: center;
            width: 90%;
        }

        h1 {
            font-size: 1.8em;
            color: #4facfe;
            margin-bottom: 20px;
        }

        label {
            font-size: 1em;
            margin-bottom: 10px;
            display: block;
        }

        input, button {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 2px solid #4facfe;
            border-radius: 5px;
            outline: none;
            font-size: 1em;
            transition: 0.3s ease-in-out;
        }

        input:focus {
            border-color: #00f2fe;
        }

        button {
            background: #4facfe;
            color: #fff;
            cursor: pointer;
            font-weight: bold;
        }

        button:hover {
            background: #00f2fe;
        }

        .result {
            margin-top: 20px;
            font-size: 1.2em;
            color: #333;
        }

        .result strong {
            color: #4facfe;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Calculateur de Mention</h1>
        <form id="noteForm">
            <label for="nbNotes">Combien de notes voulez-vous entrer ?</label>
            <input type="number" id="nbNotes" min="1" required placeholder="Ex: 5">
            <div id="notesInputs"></div>
            <button type="button" onclick="calculerMoyenne()">Calculer</button>
        </form>
        <div class="result" id="result"></div>
    </div>

    <script>
        let nbNotesInput = document.getElementById("nbNotes");
        let notesContainer = document.getElementById("notesInputs");

        // Ajouter des champs pour entrer les notes
        nbNotesInput.addEventListener("input", function () {
            let nbNotes = parseInt(nbNotesInput.value);
            notesContainer.innerHTML = ""; // Réinitialiser
            for (let i = 1; i <= nbNotes; i++) {
                let input = document.createElement("input");
                input.type = "number";
                input.placeholder = `Entrez la note ${i}`;
                input.min = "0";
                input.max = "20";
                input.required = true;
                notesContainer.appendChild(input);
            }
        });

        function calculerMention(moyenne) {
            if (moyenne < 8) return "Recalé";
            else if (moyenne < 10) return "Rattrapage";
            else if (moyenne < 12) return "Sans mention";
            else if (moyenne < 14) return "Assez bien";
            else if (moyenne < 16) return "Bien";
            else if (moyenne < 18) return "Très bien";
            else return "Félicitations";
        }

        function calculerMoyenne() {
            let notes = notesContainer.querySelectorAll("input");
            let somme = 0;
            let nbNotes = notes.length;

            // Calculer la somme des notes
            for (let note of notes) {
                somme += parseFloat(note.value) || 0;
            }

            let moyenne = somme / nbNotes;
            let mention = calculerMention(moyenne);

            // Afficher le résultat
            let resultDiv = document.getElementById("result");
            resultDiv.innerHTML = `La moyenne est de <strong>${moyenne.toFixed(2)}</strong><br>Mention : <strong>${mention}</strong>`;
        }
    </script>
</body>
</html>
