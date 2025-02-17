<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rosa Roja con Noche Estrellada y Luna</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(to bottom, #0a0a33, #1b0033);
            position: relative;
        }

        /* Luna */
        .moon {
            position: absolute;
            top: 10%;
            left: 70%;
            width: 100px;
            height: 100px;
            background: radial-gradient(circle, #fdfdfd 40%, #bbbbbb 70%);
            border-radius: 50%;
            box-shadow: 0 0 20px 5px rgba(255, 255, 255, 0.5);
        }

        /* Estrellas */
        .star {
            position: absolute;
            background-color: white;
            width: 2px;
            height: 2px;
            border-radius: 50%;
            opacity: 0;
            animation: twinkle 3s infinite ease-in-out alternate;
        }

        @keyframes twinkle {
            0% { opacity: 0; }
            50% { opacity: 1; }
            100% { opacity: 0; }
        }

        /* Contenedor de la rosa */
        .rose-container {
            position: absolute;
            bottom: 50px;
            animation: sway 3s infinite ease-in-out alternate;
        }

        @keyframes sway {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(2deg); }
        }

        /* SVG de la rosa */
        svg {
            width: 200px;
            height: 300px;
        }

        /* Animación de los pétalos */
        .petal {
            animation: bloom 2s infinite ease-in-out alternate;
        }

        @keyframes bloom {
            0% { transform: scale(1); }
            100% { transform: scale(1.05); }
        }
    </style>
</head>
<body>

    <!-- Luna -->
    <div class="moon"></div>

    <!-- Generar estrellas con JavaScript -->
    <script>
        function createStars(numStars) {
            for (let i = 0; i < numStars; i++) {
                let star = document.createElement("div");
                star.classList.add("star");
                star.style.top = Math.random() * 100 + "vh";
                star.style.left = Math.random() * 100 + "vw";
                star.style.animationDuration = Math.random() * 3 + 2 + "s";
                document.body.appendChild(star);
            }
        }
        createStars(100);
    </script>

    <!-- Contenedor de la rosa -->
    <div class="rose-container">
        <svg viewBox="0 0 200 300">
            <!-- Tallo -->
            <rect x="98" y="120" width="6" height="180" fill="green"></rect>
            
            <!-- Hojas -->
            <ellipse cx="80" cy="180" rx="25" ry="15" fill="green"></ellipse>
            <ellipse cx="120" cy="160" rx="25" ry="15" fill="green"></ellipse>
            
            <!-- Pétalos mejorados -->
            <path class="petal" d="M100,50 C130,20 160,50 140,80 C150,110 120,130 100,110 C80,130 50,110 60,80 C40,50 70,20 100,50" fill="red"/>
            <path class="petal" d="M100,50 C120,10 140,30 130,70 C140,90 110,100 100,90 C90,100 60,90 70,70 C60,30 80,10 100,50" fill="darkred"/>
            <circle class="petal" cx="100" cy="70" r="20" fill="crimson"/>
        </svg>
    </div>

</body>
</html>
