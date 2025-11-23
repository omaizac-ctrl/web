# web<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Voces Silenciadas | Archivo Desclasificado</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* Estética de la Conspiración */
        body {
            font-family: 'Roboto Mono', monospace;
            background-color: #0d0d0d; /* Negro profundo */
            color: #e0e0e0; /* Gris claro para texto */
        }
        .text-alerta {
            color: #e53e3e; /* Rojo de alerta */
        }
        .bg-clandestino {
            background-color: #1a1a1a;
        }
        .border-alerta {
            border-color: #e53e3e;
        }
        .content-section {
            display: none;
            animation: fadeIn 0.5s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .cifrado {
            background-color: #333;
            color: #333;
            user-select: none; /* Evita que se pueda seleccionar el texto para "desclasificarlo" */
            transition: all 0.3s ease;
        }
        .desclasificado:hover {
            color: #e0e0e0;
        }
        .log-simulado {
            background-color: #000;
            border-left: 3px solid #00ff00;
            padding: 8px 12px;
            color: #00ff00;
            font-size: 0.8rem;
            margin-top: 15px;
            overflow-wrap: break-word;
        }
        .loading-dot {
            animation: dot-pulse 1s infinite steps(3, start);
        }
        @keyframes dot-pulse {
            0%, 80%, 100% {
                content: '';
            }
            20% {
                content: '.';
            }
            40% {
                content: '..';
            }
            60% {
                content: '...';
            }
        }
    </style>
</head>
<body class="min-h-screen">

    <!-- CABECERA: La Interfaz de Terminal -->
    <header class="bg-clandestino border-b border-gray-800 p-4 shadow-xl">
        <div class="max-w-7xl mx-auto flex justify-between items-center">
            <h1 class="text-xl font-bold text-alerta">_VOZSILENCIADA > [MODO: CLANDESTINO]</h1>
            <div id="puntos-rigor-display" class="text-sm text-gray-400">
                Puntos de Rigor: <span id="puntos-rigor" class="text-alerta font-bold">0</span>
            </div>
        </div>
    </header>

    <main class="max-w-7xl mx-auto p-6 md:p-10">

        <!-- 1. PÁGINA DE INICIO: PUERTA DE ACCESO -->
        <section id="access-gate" class="text-center mt-20 p-8 bg-clandestino border border-alerta rounded-lg shadow-2xl">
            <p class="text-2xl font-bold text-alerta mb-6">ADVERTENCIA: ARCHIVO CLASIFICADO BAJO ALERTA ROJA.</p>
            <p class="mb-8 text-gray-300">Este archivo contiene evidencia sensible. Solo el personal autorizado (Detective Cívico) puede acceder. Introduzca la Pista Criptográfica obtenida en el último episodio.</p>

            <input type="text" id="crypto-code" placeholder="Ingrese CÓDIGO CLAVE aquí..." class="w-full max-w-sm p-3 text-center bg-gray-900 border border-gray-700 rounded-md text-alerta focus:outline-none focus:border-red-500">
            <button onclick="unlockContent()" class="mt-6 px-8 py-3 bg-alerta text-white font-bold rounded-md hover:bg-red-700 transition duration-300">
                DESBLOQUEAR ARCHIVO
            </button>
            <p id="error-message" class="text-alerta mt-4 hidden">ERROR. CÓDIGO NO VÁLIDO. INTENTE OTRA VEZ.</p>
        </section>

        <!-- Contenido Principal Desbloqueado -->
        <div id="unlocked-content" class="hidden">
            
            <!-- Menú de Navegación Clandestino -->
            <nav class="flex justify-start space-x-4 mb-8 border-b border-gray-700 pb-3">
                <button onclick="showSection('archivo')" class="nav-button text-gray-400 hover:text-alerta transition duration-200 focus:outline-none">\_ARCHIVO DESCLASIFICADO</button>
                <button onclick="showSection('forense')" class="nav-button text-gray-400 hover:text-alerta transition duration-200 focus:outline-none">\_ANÁLISIS FORENSE</button>
                <button onclick="showSection('memoria')" class="nav-button text-gray-400 hover:text-alerta transition duration-200 focus:outline-none">\_TESTIMONIOS Y MEMORIA</button>
            </nav>

            <!-- 2. SECCIÓN: EL ARCHIVO DESCLASIFICADO -->
            <section id="archivo" class="content-section">
                <h2 class="text-3xl font-bold border-l-4 border-alerta pl-4 mb-6">\_01. ARCHIVO DESCLASIFICADO</h2>
                <p class="text-gray-400 mb-8">Evidencia recuperada de la Traición de 2018 (Universo I) y notas de la investigación actual de Valeria (Universo II). Analice las tachaduras.</p>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    <!-- Documento: Informe del Coronel (Universo I) -->
                    <div class="bg-clandestino p-6 rounded-lg border border-gray-700">
                        <h3 class="text-xl font-bold text-alerta mb-3">INFORME MILITAR C0-811-A (2018)</h3>
                        <p class="text-xs text-gray-500 mb-4">ESTADO: CENSURADO - RIESGO MÁXIMO</p>
                        <p class="text-gray-300 leading-relaxed">
                            "Se procedió al protocolo de contención. La presencia de personal civil en la zona <span class="cifrado desclasificado hover:text-alerta hover:bg-transparent">pone en riesgo la integridad de la Operación Beta.</span> Se dictaminó que la prioridad era <span class="cifrado desclasificado hover:text-alerta hover:bg-transparent">evitar la fuga de información sensible</span> que pudiera comprometer al <span class="cifrado desclasificado hover:text-alerta hover:bg-transparent">Comandante Superior</span>. No se autorizó el rescate inmediato debido a <span class="text-alerta font-bold">riesgos no especificados</span> en el perímetro de seguridad..."
                        </p>
                        <p class="mt-4 text-xs text-alerta">***NOTA DE VALERIA: Las 'acciones no especificadas' son el motivo. Busquen las contradicciones en el protocolo de dotación.***</p>
                    </div>

                    <!-- Línea de Tiempo de la Tragedia (Universo I) -->
                    <div class="bg-clandestino p-6 rounded-lg border border-gray-700">
                        <h3 class="text-xl font-bold mb-3">LÍNEA DE TIEMPO (2018)</h3>
                        <p class="text-xs text-gray-500 mb-4">VERSIÓN OFICIAL VS. VERSIÓN DESCLASIFICADA</p>
                        <ul class="space-y-3 text-gray-300">
                            <li class="border-l-2 pl-3 border-green-500">Día 1: Reporte de secuestro.</li>
                            <li class="border-l-2 pl-3 border-alerta">Día 2: *Versión Oficial:* Contacto perdido. *Versión Desclasificada:* **El Coronel** recibe la petición de ayuda y la ignora.</li>
                            <li class="border-l-2 pl-3 border-alerta">Día 4: Asesinamiento. La <span class="font-bold">Pistola S-901</span> queda en la zona para ser "encontrada" por el cártel.</li>
                            <li class="border-l-2 pl-3 border-gray-500">Día 5: Retraso intencional en la difusión de la noticia a las familias.</li>
                        </ul>
                    </div>
                </div>
            </section>

            <!-- 3. SECCIÓN: ANÁLISIS FORENSE (Gamificación) -->
            <section id="forense" class="content-section">
                <h2 class="text-3xl font-bold border-l-4 border-alerta pl-4 mb-6">\_02. ANÁLISIS FORENSE</h2>
                <p class="text-gray-400 mb-8">Aquí es donde ganas Puntos de Rigor. Resuelve los retos para avanzar en el **Reportaje Oculto**.</p>
                
                <div id="analisis-pistola" class="bg-clandestino p-6 rounded-lg border border-gray-700 mb-6">
                    <h3 class="text-xl font-bold text-alerta mb-3">RETO 01: BALÍSTICA (LA PISTOLA)</h3>
                    <p class="mb-4 text-gray-300">El CÓDIGO INVERTIDO del rasguño es: **01101010011**. Necesitas el número de PROTOCOLO DE DOTACIÓN OFICIAL del modelo S-901 para desbloquear el Archivo Ortega. (Pista del Episodio 1).</p>
                    <input type="text" id="pistola-input" placeholder="Ingrese el Número de Protocolo (ej: 4070)" class="w-full max-w-md p-2 bg-gray-900 border border-gray-700 rounded-md text-alerta focus:outline-none">
                    <button onclick="checkRigor(4070, 'pistola-input', 50)" class="mt-4 px-6 py-2 bg-alerta text-white font-bold rounded-md hover:bg-red-700 transition duration-300">
                        VERIFICAR RIGOR (+50 Puntos)
                    </button>
                    <p id="pistola-feedback" class="mt-3 hidden text-sm"></p>
                </div>
                
                <div id="analisis-criptografia" class="bg-clandestino p-6 rounded-lg border border-gray-700">
                    <h3 class="text-xl font-bold mb-3">RETO 02: CRIPTOGRAFÍA (ARCHIVO ORTEGA)</h3>
                    <p class="mb-4 text-gray-300">El Archivo Ortega está protegido por un cifrado de 4 dígitos basado en la fecha de la traición militar. (Pista: La clave es la suma del día y el mes de la traición en 2018). </p>
                    <input type="text" id="cripto-input" placeholder="Ingrese el Código Cifrado (ej: 23)" class="w-full max-w-md p-2 bg-gray-900 border border-gray-700 rounded-md text-alerta focus:outline-none">
                    <button onclick="checkRigor(23, 'cripto-input', 75)" class="mt-4 px-6 py-2 bg-alerta text-white font-bold rounded-md hover:bg-red-700 transition duration-300">
                        VERIFICAR RIGOR (+75 Puntos)
                    </button>
                    <p id="cripto-feedback" class="mt-3 hidden text-sm"></p>

                    <!-- Nueva Función Gemini: Pista Criptográfica Avanzada -->
                    <button onclick="getAdvancedHint()" id="gemini-hint-button" class="mt-6 px-6 py-2 bg-purple-700 text-white font-bold rounded-md hover:bg-purple-800 transition duration-300">
                        ✨ SOLICITAR ANÁLISIS CRIPTOGRÁFICO AVANZADO
                    </button>
                    <div id="gemini-hint-output" class="log-simulado hidden"></div>
                    <p id="gemini-status" class="mt-2 text-sm text-gray-500 hidden"></p>
                </div>

            </section>

            <!-- 4. SECCIÓN: TESTIMONIOS Y MEMORIA (Universo I) -->
            <section id="memoria" class="content-section">
                <h2 class="text-3xl font-bold border-l-4 border-alerta pl-4 mb-6">\_03. TESTIMONIOS Y MEMORIA</h2>
                <p class="text-gray-400 mb-8">La voz que el Coronel intentó silenciar. Conexión directa con el trauma del Universo I.</p>
                
                <div class="bg-clandestino p-6 rounded-lg border border-gray-700">
                    <h3 class="text-xl font-bold mb-3">BITÁCORA DE ANDRÉS RIVAS (Extractos)</h3>
                    <blockquote class="border-l-4 border-gray-500 pl-4 italic text-gray-400">
                        "El dolor no fue el secuestro. El dolor fue el silencio oficial. La forma en que sabíamos que estaban vivos, y que la única razón por la que no actuaban era porque la verdad de Javier quemaba más que el peligro. Nos trataron como si fuéramos el enemigo. Y esa sensación... es lo que nos define ahora."
                    </blockquote>

                    <!-- Espacio para el Audio de Andrés Rivas (Ahora interactivo) -->
                    <div class="mt-6">
                        <h3 class="text-xl font-bold mb-3 text-alerta">ARCHIVO DE AUDIO RIVAS [TESTIMONIO]</h3>
                        <!-- El botón ahora se comporta como un enlace (<a>) en el código, pero mantiene el estilo de botón. -->
                        <a id="audio-play-link" href="https://drive.google.com/drive/folders/1mtXe1Wzi-n_Up8V3o1Hvo_E6-U5fu_F9?hl=es-419" target="_blank" disabled class="inline-block px-6 py-2 bg-gray-600 text-gray-400 font-bold rounded-md transition duration-300 opacity-50 pointer-events-none">
                            &#9654; REPRODUCIR AUDIO (BLOQUEADO)
                        </a>
                        <p id="audio-status" class="mt-2 text-sm text-gray-400">Estado: Bloqueado. Resuelve el Reto 02 para acceder.</p>
                    </div>

                </div>
                
                <div class="bg-clandestino p-6 rounded-lg border border-gray-700 mt-6">
                    <h3 class="text-xl font-bold mb-3">EL LLAMADO A LA VIGILANCIA</h3>
                    <p class="text-gray-300 mb-4">El Reportaje Oculto solo se mantiene vivo si la comunidad actúa. Únete al **Cuarto de Guerra Digital**.</p>
                    <a href="https://t.me/vocesilenciadas" target="_blank" class="px-6 py-2 bg-blue-600 text-white font-bold rounded-md hover:bg-blue-700 transition duration-300">
                        UNIRSE A TELEGRAM (CUARTO DE GUERRA)
                    </a>
                </div>
            </section>
        </div>
    </main>

    <!-- Modal de Notificación -->
    <div id="modal-container" class="fixed inset-0 bg-black bg-opacity-80 items-center justify-center hidden">
        <div class="bg-clandestino p-8 rounded-lg border-2 border-alerta shadow-2xl max-w-sm text-center">
            <p id="modal-message" class="text-xl font-bold text-alerta mb-4"></p>
            <button onclick="closeModal()" class="px-6 py-2 bg-alerta text-white font-bold rounded-md hover:bg-red-700 transition duration-300">
                CERRAR
            </button>
        </div>
    </div>

    <script>
        let isContentUnlocked = false;
        let puntosRigor = 0;
        const correctCode = "011010100114070"; // Ejemplo de código concatenado
        
        // --- Configuración de la API de Gemini ---
        const apiKey = ""; 
        const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`;

        // Función para mostrar el modal
        function showModal(message) {
            document.getElementById('modal-message').innerText = message;
            document.getElementById('modal-container').classList.remove('hidden');
            document.getElementById('modal-container').classList.add('flex');
        }

        // Función para cerrar el modal
        function closeModal() {
            document.getElementById('modal-container').classList.remove('flex');
            document.getElementById('modal-container').classList.add('hidden');
        }

        // Función para desbloquear el contenido
        function unlockContent() {
            const inputCode = document.getElementById('crypto-code').value.trim();
            const errorMessage = document.getElementById('error-message');

            if (inputCode === correctCode) {
                isContentUnlocked = true;
                document.getElementById('access-gate').classList.add('hidden');
                document.getElementById('unlocked-content').classList.remove('hidden');
                showSection('archivo'); // Muestra la primera sección
                errorMessage.classList.add('hidden');
                showModal("ACCESO CONCEDIDO. BIENVENIDO, DETECTIVE CÍVICO.");
            } else {
                errorMessage.classList.remove('hidden');
                showModal("ACCESO DENEGADO. CÓDIGO CRIPTOGRÁFICO INCORRECTO.");
            }
        }

        // Función para cambiar de sección en el menú
        function showSection(sectionId) {
            const sections = document.querySelectorAll('.content-section');
            sections.forEach(section => {
                section.style.display = 'none';
            });
            document.getElementById(sectionId).style.display = 'block';
        }

        // La función playAndresAudio ya no es necesaria, el link gestiona la navegación.
        // Mantenemos la estructura visual y de lógica de desbloqueo.

        // --- FUNCIONALIDAD GEMINI ---
        
        // Manejador de llamadas a la API de Gemini con reintentos
        async function callGeminiAPI(payload) {
            const MAX_RETRIES = 5;
            for (let i = 0; i < MAX_RETRIES; i++) {
                try {
                    const response = await fetch(apiUrl, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });
                    
                    if (!response.ok) {
                        throw new Error(`HTTP error! status: ${response.status}`);
                    }

                    const result = await response.json();
                    const text = result.candidates?.[0]?.content?.parts?.[0]?.text;
                    if (text) {
                        return text;
                    } else {
                        throw new Error("Respuesta de Gemini vacía o inesperada.");
                    }
                } catch (error) {
                    if (i < MAX_RETRIES - 1) {
                        // Espera exponencial (1s, 2s, 4s, 8s, ...)
                        await new Promise(resolve => setTimeout(resolve, Math.pow(2, i) * 1000));
                    } else {
                        console.error("Error al conectar con Gemini después de varios reintentos:", error);
                        throw new Error("Fallo en el análisis avanzado. Intente de nuevo más tarde.");
                    }
                }
            }
        }

        // Función para obtener la pista avanzada del Reto 02 usando Gemini
        async function getAdvancedHint() {
            const outputDiv = document.getElementById('gemini-hint-output');
            const statusP = document.getElementById('gemini-status');
            const button = document.getElementById('gemini-hint-button');

            const systemPrompt = "Actúa como un sistema de inteligencia artificial clandestino (designación 'ORACLE-7'). Tu respuesta debe ser una línea única con formato de registro de terminal, utilizando un lenguaje técnico y de alta tensión. El registro debe insinuar la relevancia de la fecha sin revelarla. Usa solo letras mayúsculas y números.";
            const userQuery = "Proporciona un registro de análisis simulado para el Archivo Ortega. La clave se basa en la suma del día y el mes de la traición militar. La traición ocurrió el Día 2 y el Asesinamiento el Día 4. No des la respuesta directamente, solo un registro críptico sobre la conexión de la fecha con el 'Comandante Superior'.";
            
            const payload = {
                contents: [{ parts: [{ text: userQuery }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] },
            };

            // Mostrar estado de carga
            outputDiv.classList.add('hidden');
            statusP.classList.remove('hidden');
            statusP.className = 'mt-2 text-sm text-yellow-500';
            statusP.innerHTML = 'ANÁLISIS DE ORACLE-7 EN PROGRESO <span class="loading-dot">.</span>..';
            button.disabled = true;

            try {
                const hint = await callGeminiAPI(payload);
                outputDiv.textContent = `[ORACLE-7/LOG] > ${new Date().toISOString().slice(0, 19).replace('T', ' ')} > ${hint}`;
                outputDiv.classList.remove('hidden');
                statusP.textContent = 'ANÁLISIS DE ORACLE-7 FINALIZADO. DATOS OBTENIDOS.';
                statusP.className = 'mt-2 text-sm text-green-500';
                
            } catch (error) {
                outputDiv.textContent = `[ERROR_FATAL] > FALLO DE CONEXIÓN CON ORACLE-7: ${error.message}`;
                outputDiv.classList.remove('hidden');
                statusP.textContent = 'ERROR DE CONEXIÓN. Intente re-inicializar el módulo.';
                statusP.className = 'mt-2 text-sm text-alerta';
            } finally {
                button.disabled = false;
            }
        }
        
        // Función de gamificación para verificar el rigor
        function checkRigor(correctAnswer, inputId, points) {
            const inputElement = document.getElementById(inputId);
            const feedbackElement = document.getElementById(inputId.replace('-input', '-feedback'));
            const inputValue = inputElement.value.trim();

            // Convierte el valor a número si la respuesta correcta es un número
            const checkValue = typeof correctAnswer === 'number' ? parseInt(inputValue) : inputValue;

            feedbackElement.classList.remove('hidden');

            if (checkValue === correctAnswer) {
                if (inputElement.disabled) {
                    feedbackElement.textContent = "ESTE RETO YA FUE RESUELTO. RIGOR VALIDADO.";
                    feedbackElement.className = 'mt-3 text-sm text-green-500';
                    return;
                }

                puntosRigor += points;
                document.getElementById('puntos-rigor').textContent = puntosRigor;
                feedbackElement.textContent = `¡RIGOR VALIDADO! Has ganado +${points} Puntos de Rigor.`;
                feedbackElement.className = 'mt-3 text-sm text-green-500';
                inputElement.disabled = true; // Deshabilita el input después de un éxito
                inputElement.value = inputValue; // Mantiene el valor correcto
                
                showModal(`¡RIGOR VALIDADO! Ganaste ${points} Puntos. Continúa la investigación.`);

                // Lógica para desbloquear el Audio de Andrés
                if (inputId === 'cripto-input' && puntosRigor >= 75) {
                    const audioLink = document.getElementById('audio-play-link');
                    const audioStatus = document.getElementById('audio-status');
                    
                    // Desbloquea el enlace
                    audioLink.classList.remove('opacity-50', 'pointer-events-none');
                    audioLink.classList.remove('bg-gray-600', 'text-gray-400');
                    audioLink.classList.add('bg-green-600', 'text-white', 'hover:bg-green-700');
                    audioLink.textContent = '▶ ACCEDER AL TESTIMONIO RIVAS (Drive)';
                    
                    audioStatus.textContent = 'Estado: DESBLOQUEADO. Haz clic para acceder a la evidencia de audio.';
                }

            } else {
                feedbackElement.textContent = "VERIFICACIÓN FALLIDA. Los datos no concuerdan. Intente cotejar la información con la Línea de Tiempo.";
                feedbackElement.className = 'mt-3 text-sm text-alerta';
            }
        }

        // Inicializar mostrando la puerta de acceso
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('access-gate').classList.remove('hidden');
        });
    </script>
</body>
</html>
