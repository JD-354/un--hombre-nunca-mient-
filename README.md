<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(45deg, #000000, #003300);
            color: white;
            min-height: 100vh;
            position: relative;
        }

        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            text-align: center;
            padding: 40px 0;
            background: rgba(0, 0, 0, 0.5);
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.2);
            transform-style: preserve-3d;
            animation: float 6s ease-in-out infinite;
        }

        h1 {
            font-size: 3em;
            color: #00ff00;
            text-shadow: 0 0 10px rgba(0, 255, 0, 0.5);
            margin-bottom: 20px;
        }

        .materia {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .materia {
            background: rgba(0, 51, 0, 0.7);
            padding: 25px;
            border-radius: 15px;
            transition: transform 0.3s ease;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0, 255, 0, 0.1);
        }

        .materia:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 255, 0, 0.2);
        }

        .materia h2 {
            color: #00ff00;
            margin-bottom: 15px;
        }

        .btn {
            display: inline-block;
            padding: 12px 25px;
            background: linear-gradient(45deg, #00ff00, #006600);
            color: white;
            text-decoration: none;
            border-radius: 25px;
            transition: transform 0.3s ease;
            margin-top: 15px;
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            transform: scale(1.05);
        }

        .formulario {
            background: rgba(0, 51, 0, 0.7);
            padding: 30px;
            border-radius: 15px;
            margin-top: 40px;
        }

        .formulario input, .formulario textarea {
            width: 100%;
            padding: 12px;
            margin-bottom: 20px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.1);
            color: white;
        }

        .servicios {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .servicios {
            background: linear-gradient(45deg, #001a00, #003300);
            padding: 30px;
            border-radius: 15px;
            max-width: 600px;
            width: 90%;
            position: relative;
            animation: modalAppear 0.3s ease-out;
        }

        @keyframes modalAppear {
            from {
                transform: scale(0.7);
                opacity: 0;
            }
            to {
                transform: scale(1);
                opacity: 1;
            }
        }

        .close-modal {
            position: absolute;
            right: 20px;
            top: 15px;
            font-size: 24px;
            cursor: pointer;
            color: #00ff00;
        }

        .materias-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .materia {
            background: rgba(0, 51, 0, 0.5);
            padding: 15px;
            border-radius: 10px;
            text-align: center;
        }

        .estadisticas {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin: 40px 0;
            text-align: center;
        }

        .estadistica {
            background: rgba(0, 51, 0, 0.7);
            padding: 20px;
            border-radius: 10px;
        }

        .numero {
            font-size: 2.5em;
            color: #00ff00;
            margin-bottom: 10px;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }
    </style>
</head>
<body>
    <canvas class="particles"></canvas>
    <div class="container">
        <header>

    <div id="modal-tutoria" class="materia">
        <div class="modal-content">
            <span class="materia" onclick="closeModal('tutoria')">&times;</span>
            <h1>Programa de Tutoría Personalizada</h1>
            <h1>Materias Disponibles:</h1>
            </header>

            <div class="materia">
                <h2>Matemáticas</h2>
                    <p>Algebra, cálculo, Geometría</p><button onclick="openModal('otros apoyos')" class="btn">comenzar classes</button>
                    </div>
                <div class="materia">
                    <h2>Ciencias</h2>
                    <p>Física, Química, Biología</p><button onclick="openModal('otros apoyos')" class="btn">comenzar classes</button>
                </div>
                <div class="materia">
                    <h2>Lenguaje</h2>
                    <p>Comprensión, Redacción</p><button onclick="openModal('otros apoyos')" class="btn">comenzar classes</button>
                </div>
                <div class="materia">
                    <h2>Inglés</h2>
                    <p>Todos los niveles</p><button onclick="openModal('otros apoyos')" class="btn">comenzar classes</button>
                </div>
                
            </div>
            <p style="margin-top: 20px;">Metodología:</p>
            <ul style="margin-left: 20px;">
                <li>Evaluación inicial gratuita</li>
                <li>Plan de estudio personalizado</li>
                <li>Seguimiento continuo</li>
                <li>Reportes de progreso mensuales</li>
            </ul>
        </div>
    </div>
    <script>
        // Código de partículas (mantener el mismo)
        const canvas = document.querySelector('.particles');
        const ctx = canvas.getContext('2d');
        let particles = [];

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 3;
                this.speedX = Math.random() * 3 - 1.5;
                this.speedY = Math.random() * 3 - 1.5;
            }

            update() {
                this.x += this.speedX;
                this.y += this.speedY;

                if (this.x > canvas.width) this.x = 0;
                if (this.x < 0) this.x = canvas.width;
                if (this.y > canvas.height) this.y = 0;
                if (this.y < 0) this.y = canvas.height;
            }

            draw() {
                ctx.fillStyle = '#00ff00';
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function init() {
            for (let i = 0; i < 100; i++) {
                particles.push(new Particle());
            }
        }

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for (let particle of particles) {
                particle.update();
                particle.draw();
            }
            requestAnimationFrame(animate);
        }

        init();
        animate();

        // Funciones para los modales
        function openModal(type) {
            document.getElementById(modal-$,{type}).style.display = 'flex';
        }

        function closeModal(type) {
            document.getElementById(modal-$,{type}).style.display = 'none';
        }

        
        </script>


</body>
</html>
