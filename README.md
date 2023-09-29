# Astral
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Examen de Fisiología Cardíaca</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        .question {
            margin-bottom: 20px;
        }
        .correct {
            color: green;
        }
        .incorrect {
            color: red;
        }
    </style>
</head>
<body>
    <h1>Examen de Fisiología Cardíaca</h1>

    <form id="examForm">
        <div class="question">
            <p>1. ¿Cuál de las siguientes afirmaciones sobre el corazón es correcta?</p>
            <label><input type="radio" name="q1" value="a"> a) El corazón derecho bombea sangre hacia los pulmones.</label><br>
            <label><input type="radio" name="q1" value="b"> b) El ventrículo izquierdo bombea sangre pobre en oxígeno.</label><br>
            <label><input type="radio" name="q1" value="c"> c) Las aurículas reciben sangre de los vasos sanguíneos.</label><br>
            <label><input type="radio" name="q1" value="d"> d) Todas las anteriores.</label>
        </div>
        
        <div class="question">
            <p>2. ¿Cuál es la función principal del sistema de conducción eléctrica del corazón?</p>
            <label><input type="radio" name="q2" value="a"> a) Generar impulsos eléctricos para contraer los músculos.</label><br>
            <label><input type="radio" name="q2" value="b"> b) Mantener el ritmo cardíaco en reposo.</label><br>
            <label><input type="radio" name="q2" value="c"> c) Conducir impulsos eléctricos para sincronizar la contracción cardíaca.</label><br>
            <label><input type="radio" name="q2" value="d"> d) Regular el volumen de sangre en el corazón.</label>
        </div>
        
        <!-- Aquí irían las demás preguntas en un formato similar -->
        
        <input type="button" value="Revisar Respuestas" onclick="checkAnswers()">
    </form>
    
    <script>
        function checkAnswers() {
            // Respuestas correctas
            var correctAnswers = {
                q1: "d",
                q2: "c",
                // Aquí irían las respuestas correctas de las demás preguntas
            };
            
            // Inicializar las respuestas del usuario
            var userAnswers = {};
            
            // Obtener las respuestas del usuario y marcarlas como correctas o incorrectas
            for (var question in correctAnswers) {
                var selectedOption = document.querySelector('input[name="' + question + '"]:checked');
                userAnswers[question] = selectedOption ? selectedOption.value : null;
                
                if (selectedOption) {
                    selectedOption.parentElement.classList.add(userAnswers[question] === correctAnswers[question] ? 'correct' : 'incorrect');
                }
            }
            
            // Comparar las respuestas del usuario con las correctas y calcular la puntuación
            var score = 0;
            for (var question in correctAnswers) {
                if (correctAnswers[question] === userAnswers[question]) {
                    score++;
                }
            }
            
            // Mostrar la puntuación
            alert("Tu puntuación es: " + score + " de " + Object.keys(correctAnswers).length);
        }
    </script>
</body>
</html>
