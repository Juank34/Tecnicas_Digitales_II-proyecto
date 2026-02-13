
📡 STM32 Smart Tracking & Scanning Node
Proyecto desarrollado con STM32F103C8T6 (Blue Pill)
📌 Descripción
Este proyecto implementa un sistema embebido interactivo con interfaz gráfica, basado en el microcontrolador STM32F103C8T6, que combina:
Menú gráfico navegable
Seguimiento automático de objetos
Escaneo tipo radar
Control de brillo por ADC + DMA + PWM
El sistema utiliza sensores ultrasónicos, servomotor, display gráfico a color ILI9341 y control por pulsadores, integrando múltiples periféricos del STM32.
🧰 Hardware Utilizado
🔵 STM32F103C8T6 (Blue Pill)
🖥 Display TFT color ILI9341 (240x320, SPI)
📡 2x Sensores ultrasónicos (HC-SR04 o similar)
⚙️ 1x Servomotor (rotación 0°–180°)
🔘 3x Pulsadores (UP / DOWN / ENTER)
🎚 2x Potenciómetros
🔴 LED rojo
🔵 LED azul
🧲 Solenoide (activación mecánica)
🖥 Interfaz de Usuario
El sistema posee un menú gráfico con 4 opciones, navegable mediante:
Pulsador UP → Subir opción
Pulsador DOWN → Bajar opción
Pulsador ENTER → Seleccionar
El menú y las gráficas se renderizan en el display ILI9341, utilizando comunicación SPI.
📋 Modos de Funcionamiento
1️⃣ Modo Seguimiento (Tracking Mode)
Los dos sensores ultrasónicos detectan un objeto al frente.
Se calcula la posición relativa del objeto.
El servomotor ajusta su ángulo hacia la nueva posición detectada.
Funciona como un nodo de captura y seguimiento automático.
📌 Aplicación tipo:
Sistema de tracking
Torreta de seguimiento
Nodo inteligente de captura
2️⃣ Modo Escaneo / Radar
El servo realiza un barrido de 0° a 180° y regreso (180° → 0°).
Durante el movimiento, los sensores ultrasónicos miden distancia.
El display ILI9341 grafica en tiempo real si se detecta un objeto.
Simula un radar de barrido angular.
📊 El resultado se muestra gráficamente en el TFT a color.
3️⃣ Información del Proyecto
Muestra en pantalla:
Nombre del proyecto
Autores
Información académica
4️⃣ Modo ADC + DMA + PWM
Se utilizan 2 canales ADC en modo DMA.
Cada potenciómetro controla independientemente el brillo de:
🔴 LED rojo
🔵 LED azul
La señal ADC se convierte en ciclo útil PWM.
Control completamente independiente y en tiempo real.
🎯 Se demuestra:
Uso de ADC
Uso de DMA
Generación PWM
Control multitarea embebido
⚙️ Periféricos STM32 Utilizados
GPIO
ADC (modo scan)
DMA
TIM (PWM)
Interrupciones externas
Control de servo por PWM
Comunicación SPI para display ILI9341
🧠 Conceptos Implementados
Máquina de estados para menú
Navegación por pulsadores con debounce
Barrido angular con servo
Adquisición de datos por DMA
Control en tiempo real
Representación gráfica en TFT ILI9341
Sistema multitarea simple
🚀 Aplicaciones
Nodo de detección inteligente
Sistema tipo radar educativo
Plataforma didáctica STM32
Proyecto académico de electrónica embebida
📷 Posibles Mejoras Futuras
Filtro digital para mediciones espurias
Interfaz gráfica más avanzada
Comunicación UART / USB
Registro de datos
Algoritmo PID para seguimiento más preciso
Optimización del renderizado en ILI9341
