
<html lang="en">

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estudiantes sin Límites</title>
</head>
<body>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
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

        .servicios {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .servicio {
            background: rgba(0, 51, 0, 0.7);
            padding: 25px;
            border-radius: 15px;
            transition: transform 0.3s ease;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0, 255, 0, 0.1);
        }

        .servicio:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 255, 0, 0.2);
        }

        .servicio h3 {
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

        .modal {
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

        .modal-content {
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
            <h1>Estudiantes sin Límites</h1>
            <h1>Potencia tu Rendimiento Académico</h1>
                    <h1>Descubre tu máximo potencial con nuestro programa de apoyo integral</h1>
                    
            
            
            <p>Transformando el futuro académico, un estudiante a la vez</p>

        </header>

        <div class="estadisticas">
            <div class="estadistica">
                <div class="numero">500+</div>
                <p>Estudiantes Ayudados</p>
            </div>
            <div class="estadistica">
                <div class="numero">95%</div>
                <p>Tasa de Mejora</p>
            </div>
            <div class="estadistica">
                <div class="numero">50+</div>
                <p>Tutores Expertos</p>
            </div>
            <div class="estadistica">
                <div class="numero">8</div>
                <p>Años de Experiencia</p>
            </div>
        </div>
        <div class="servicio">
        <div class="servicios">

            <div class="servicio">
                <h3>Tutoría Personalizada</h3>
                        <p>Apoyo individual adaptado a tus necesidades específicas en todas las materias.</p><button onclick="openModal('otros apoyos')" class="btn">totoriar.</button><a href="./tutorias per.html" class="button"> .tutorial  </a> 
                        </div>
            <div class="servicio">🧠
                <h3>Apoyo Psicoeducativo</h3>
                <p>Orientación para superar bloqueos y desarrollar habilidades de aprendizaje.</p>   <button onclick="openModal('otros apoyos')" class="btn">Ver</button>
            </div>
            <div class="servicio">
                <h3>Talleres de Estudio</h3>
                <p>Aprende técnicas efectivas de estudio, gestión del tiempo y organización para mejorar tu rendimiento académico.</p>
                <button onclick="openModal('talleres')" class="btn">Inscríbete Ahora</button>
            </div>
            <div class="servicio">
                <h3>Apoyo </h3>
                <p>Asesoramiento profesional para superar bloqueos de aprendizaje y desarrollar una mentalidad positiva.</p>
                <button onclick="openModal('apoyo')" class="btn">Consulta Gratis</button>
            </div>
            <div class="servicio">🎯
                        <h3>Técnicas de Estudio</h3>
                        <p>Aprende métodos efectivos para mejorar tu comprensión y retención.</p>
        </div>
        <div class="servicio">
        <h3>Tutoría unico</h3>
                        <p>Apoyo individual adaptado a tus necesidades específicas en todas las materias.</p><button onclick="openModal('otros apoyos')" class="btn">tutoria</button>
                    </di>

          </div>  

        <div class="formulario">
            <section class="hero" >
            <h2>¿Necesitas ayuda? ¡Contáctanos!</h2>
            <form onsubmit="return handleSubmit(event)">
                <input type="text" placeholder="Nombre completo" required>
                <input type="email" placeholder="Correo electrónico" required>
                <textarea placeholder="Cuéntanos sobre tus necesidades académicas" rows="5" required></textarea>
                
    <div id="modal-tutoria" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('tutoria')">&times;</span>
            <h2>Programa de Tutoría Personalizada</h2>
            <h3>Materias Disponibles:</h3>
            <div class="materias-grid">
                <div class="materia">
                    <h4>Matemáticas</h4>
                    <p>Álgebra, Cálculo, Geometría</p>
                </div>
                <div class="materia">
                    <h4>Ciencias</h4>
                    <p>Física, Química, Biología</p>
                </div>
                <div class="materia">
                    <h4>Lenguaje</h4>
                    <p>Comprensión, Redacción</p>
                </div>
                <div class="materia">
                    <h4>Inglés</h4>
                    <p>Todos los niveles</p>
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
</body>
    <div id="modal-talleres" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('talleres')">&times;</span>
            <h2>Talleres de Estudio</h2>
            <h3>Próximos Talleres:</h3>
            <div class="materias-grid">
                <div class="materia">
                    <h4>Técnicas de Estudio</h4>
                    <p>Duración: 4 semanas</p>
                </div>
                <div class="materia">
                    <h4>Gestión del Tiempo</h4>
                    <p>Duración: 2 semanas</p>
                </div>
                <div class="materia">
                    <h4>Preparación de Exámenes</h4>
                    <p>Duración: 3 semanas</p>
                </div>
                <div class="materia">
                    <h4>Memoria y Concentración</h4>
                    <p>Duración: 2 semanas</p>
                </div>
            </div>
            <p style="margin-top: 20px;">Beneficios:</p>
            <ul style="margin-left: 20px;">
                <li>Grupos reducidos</li>
                <li>Material didáctico incluido</li>
                <li>Certificado de participación</li>
                <li>Seguimiento post-taller</li>
            </ul>
        </div>
    </div>

    <div id="modal-apoyo" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('apoyo')">&times;</span>
            <h2>Apoyo Psicoeducativo</h2>
            <h3>Servicios Disponibles:</h3>
            <div class="materias-grid">
                <div class="materia">
                    <h4>Diagnóstico</h4>
                    <p>Evaluación inicial</p>
                </div>
                <div class="materia">
                    <h4>Orientación</h4>
                    <p>Plan personalizado</p>
                </div>
                <div class="materia">
                    <h4>Seguimiento</h4>
                    <p>Apoyo continuo</p>
                </div>
                <div class="materia">
                    <h4>Familia</h4>
                    <p>Orientación familiar</p>
                </div>
            </div>
            <p style="margin-top: 20px;">Áreas de apoyo:</p>
            <ul style="margin-left: 20px;">
                <li>Ansiedad académica</li>
                <li>Motivación escolar</li>
                <li>Hábitos de estudio</li>
                <li>Autoestima académica</li>
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
           
