# Carta-amor
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rompecabezas de Amor</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #fbe3e8;
        }
        #carta-animada {
            width: 150px;
            height: 150px;
            background-image: url('carta-animada.gif'); /* Imagen animada de la carta */
            background-size: cover;
            margin: 20px auto;
        }
        #mensaje {
            font-size: 20px;
            background-color: #ff6b81;
            color: white;
            padding: 10px;
            cursor: pointer;
            border-radius: 5px;
            display: inline-block;
            margin-top: 20px;
        }
        #puzzle-container {
            display: grid;
            grid-template-columns: repeat(3, 100px);
            grid-gap: 5px;
            width: 315px;
            margin: 20px auto;
            display: none;
        }
        .puzzle-piece {
            width: 100px;
            height: 100px;
            background-size: 300px 300px;
            opacity: 0;
            transition: opacity 0.5s ease-in-out;
        }
        #mensaje-final {
            font-size: 24px;
            font-weight: bold;
            color: #d10060;
            margin-top: 20px;
            display: none;
        }
    </style>
</head>
<body>
    <div id="carta-animada"></div>
    <div id="mensaje" onclick="iniciarRompecabezas()">Te llegó una carta, ábrela</div>
    <div id="puzzle-container">
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: 0 0;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: -100px 0;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: -200px 0;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: 0 -100px;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: -100px -100px;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: -200px -100px;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: 0 -200px;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: -100px -200px;"></div>
        <div class="puzzle-piece" style="background-image: url('carta.jpg'); background-position: -200px -200px;"></div>
    </div>
    <div id="mensaje-final">Desde que llegaste a mi vida todo fue para mejor y eso nadie jamás logrará, te amo</div>
    
    <script>
        function iniciarRompecabezas() {
            document.getElementById("mensaje").style.display = "none";
            let piezas = document.querySelectorAll(".puzzle-piece");
            document.getElementById("puzzle-container").style.display = "grid";
            
            piezas.forEach((pieza, index) => {
                setTimeout(() => {
                    pieza.style.opacity = "1";
                }, index * 500);
            });
            
            setTimeout(() => {
                document.getElementById("mensaje-final").style.display = "block";
            }, piezas.length * 500 + 1000);
        }
    </script>
</body>
</html>
