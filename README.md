<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estudiantes Sin Límites - 3D</title>

</head>
<body>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            overflow-x: hidden;
            background: #000;
        }

        #canvas-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }

        .content {
            position: relative;
            z-index: 2;
            color: white;
        }

        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1rem 2rem;
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #fff;
            text-shadow: 0 0 10px rgba(0, 255, 255, 0.5);
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            margin-left: 2rem;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            transition: all 0.3s;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .nav-links a:hover {
            background: rgba(255, 255, 255, 0.1);
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.3);
        }

        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 2rem;
            background: rgba(0, 0, 0, 0.5);
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            max-width: 600px;
        }

        .cta-button {
            background: linear-gradient(45deg, #00ffff, #00ff88);
            color: black;
            padding: 1rem 2rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.3);
        }

        .cta-button:hover {
            transform: scale(1.1);
            box-shadow: 0 0 30px rgba(0, 255, 255, 0.5);
        }

        .share-link {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: rgba(0, 0, 0, 0.7);
            padding: 1rem 2rem;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.3);
            z-index: 1000;
        }

        .share-link input {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            padding: 0.5rem 1rem;
            border-radius: 10px;
            color: white;
            margin-right: 1rem;
            width: 300px;
        }

        .share-link button {
            background: linear-gradient(45deg, #00ffff, #00ff88);
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .share-link button:hover {
            transform: scale(1.1);
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .nav-links {
                display: none;
            }

            .share-link {
                bottom: 1rem;
                right: 1rem;
                left: 1rem;
            }

            .share-link input {
                width: calc(100% - 100px);
            }
        }
    </style>
</head>
<body>
    <div id="canvas-container"></div>

    <div class="content">
        <nav class="navbar">
            <div class="logo">Estudiantes Sin Límites</div>
            <div class="nav-links">
                <a href="#inicio">Inicio</a>
                <a href="#servicios">Servicios</a>
                <a href="#contacto">Contacto</a>
            </div>
        </nav>

        <section class="hero">
            <h1>Estudiantes Sin Límites</h1>
            <p>Descubre una nueva dimensión en el aprendizaje con nuestra plataforma educativa revolucionaria</p>
            <a href="./estu3.html" class="cta-button">Comienza tu Viaje</a>
            <link rel="stylesheet" href="./estu3.html"
        </section>

        <div class="share-link">
            <input type="text" value="content://com.whatsapp.provider.media/item/estu3.html" readonly>
            <button onclick="copyLink()">Copiar</button>
        </div>
    </div>

    <script>
        // Configuración de Three.js
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.getElementById('canvas-container').appendChild(renderer.domElement);

        // Crear partículas para el efecto de fondo
        const particlesGeometry = new THREE.BufferGeometry();
        const particlesCount = 5000;
        const posArray = new Float32Array(particlesCount * 3);

        for(let i = 0; i < particlesCount * 3; i++) {
            posArray[i] = (Math.random() - 0.5) * 5;
        }

        particlesGeometry.setAttribute('position', new THREE.BufferAttribute(posArray, 3));

        const particlesMaterial = new THREE.PointsMaterial({
            size: 0.005,
            color: 0x00ffff,
        });

        const particlesMesh = new THREE.Points(particlesGeometry, particlesMaterial);
        scene.add(particlesMesh);

        camera.position.z = 2;

        // Animación
        function animate() {
            requestAnimationFrame(animate);
            particlesMesh.rotation.y += 0.001;
            particlesMesh.rotation.x += 0.001;
            renderer.render(scene, camera);
        }
        animate();

        // Responsive
        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });

        // Función para copiar el link
        function copyLink() {
            const input = document.querySelector('.share-link input');
            input.select();
            document.execCommand('copy');
            alert('¡Link copiado al portapapeles!');
        }

        // Efecto de movimiento con el mouse
        document.addEventListener('mousemove', (event) => {
            const mouseX = event.clientX / window.innerWidth - 0.5;
            const mouseY = event.clientY / window.innerHeight - 0.5;
            
            particlesMesh.rotation.y = mouseX * 0.5;
            particlesMesh.rotation.x = mouseY * 0.5;
        });
    </script>

</body>
</html>

