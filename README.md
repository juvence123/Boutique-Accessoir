<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Vote des étudiants</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f2f2f2;
        }
        .container {
            background: white;
            padding: 20px;
            margin: 50px auto;
            width: 300px;
            border-radius: 10px;
            box-shadow: 0 0 10px gray;
        }
        button {
            margin: 10px;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .btn1 { background-color: #4CAF50; color: white; }
        .btn2 { background-color: #2196F3; color: white; }
    </style>
</head>
<body>

<div class="container">
    <h2>Vote ton choix</h2>
    <p>Quel est ton choix entre Mampilalao ou Mampianatra ?</p>

    <button class="btn1" onclick="voter('Choix 1')">Choix 1</button>
    <button class="btn2" onclick="voter('Choix 2')">Choix 2</button>

    <h3 id="resultat"></h3>
</div>

<script>
    let votes = {
        "Mampilalao": 0,
        "Mampianatra": 0
    };

    function voter(choix) {
        votes[choix]++;
        afficherResultat();
    }

    function afficherResultat() {
        document.getElementById("resultat").innerHTML =
            "Mampilalao : " + votes["Choix 1"] + " votes<br>" +
            "Mampianatra : " + votes["Choix 2"] + " votes";
    }
</script>

</body>
</html>
