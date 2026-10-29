Registro de Interacciones y Documentación Técnica de Prompts

Proyecto: Landing Page del Museo de Ciencias Naturales de San Cristóbal

Materia: Tecnología de la Información | Tecnicatura Superior en Desarrollo de Software (1.er Año)

Alumno: Juan Pablo Moyano

Institución: Escuela Normal Superior N° 40 "Mariano Moreno"

📌 Introducción y Metodología de Trabajo

El desarrollo del proyecto fue dirigido y maquetado por el alumno, utilizando datos institucionales reales del Museo de Ciencias Naturales de San Cristóbal (ubicación, colecciones, historia y radio comunitaria).

La Inteligencia Artificial se utilizó de forma estratégica como herramienta de soporte técnico para la resolución de patrones visuales específicos, optimizaciones de diseño responsivo, personalización de íconos temáticos y para el desarrollo del script de Modo Oscuro en JavaScript (requerimiento adicional para la promoción de la materia).

🛠️ Detalle de Tareas, Requerimientos y Soluciones Técnicas

Tarea 1: Generación e Iconografía del Cardenal Amarillo

Requerimiento: A partir del logo del museo que representa un cardenal amarillo, se requirió asistencia para definir e integrar una representación gráfica minimalista que funcione como ícono identificatorio del sitio.

Solución Técnica: Implementación de un contenedor de ícono estilizado con clases CSS y estilos alineados a la paleta institucional (var(--primary)).

<!-- Estructura de ícono temático para avifauna -->
<div class="info-icon">
    <i class="fa-solid fa-feather-pointed"></i>
</div>


.info-icon {
  font-size: 2.2rem;
  color: var(--primary);
  margin-bottom: 0.75rem;
}


Tarea 2: Integración Multimedia de la Radio Comunitaria

Requerimiento: Estructurar un módulo interactivo para la Radio Comunitaria Científica del museo, incorporando un reproductor de audio nativo con diseño adaptado a la estética general.

Solución Técnica: Maquetado del componente con la etiqueta semántica <audio> estilizada mediante CSS.

<div class="radio-card">
    <div class="radio-icon"><i class="fa-solid fa-radio"></i></div>
    <h3>Radio Comunitaria Científica</h3>
    <p>Emisión en vivo de contenido educativo y divulgación científica.</p>
    <audio controls class="audio-player">
        <source src="audio/transmision-demo.mp3" type="audio/mpeg">
        Tu navegador no soporta el reproductor de audio.
    </audio>
</div>


Tarea 3: Animaciones de Despliegue para Colecciones (Estilo Louvre)

Requerimiento: Diseñar una galería interactiva para las 6 exposiciones del museo que responda con efectos de animación al pasar el cursor o interactuar en pantallas táctiles.

Solución Técnica: Uso de CSS Grid y transiciones sobre las tarjetas (transform y box-shadow) para generar el efecto de elevación y despliegue.

.collection-card {
  position: relative;
  border-radius: var(--radius);
  overflow: hidden;
  transition: var(--transition);
  cursor: pointer;
}

.collection-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 25px rgba(0, 0, 0, 0.25);
}


Tarea 4: Grilla Responsiva para Mapa y Ubicación

Requerimiento: Integrar la ubicación oficial (H. Irigoyen y Dr. G. Lassaga) combinando la información de accesibilidad y el iframe del mapa interactivo de Google Maps en un diseño adaptativo de dos columnas.

Solución Técnica: Definición de una grilla en dos columnas con ajuste automático a una sola columna mediante media queries para dispositivos móviles.

<section id="ubicacion" class="section bg-light">
    <div class="container">
        <div class="location-grid">
            <div class="location-info">
                <h3>Ubicación y Entorno</h3>
                <p>H. Irigoyen y Dr. Gerónimo Lassaga, San Cristóbal, Santa Fe.</p>
            </div>
            <div class="map-container">
                <iframe src="https://www.google.com/maps/embed?pb=..." width="100%" height="350" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
            </div>
        </div>
    </div>
</section>


.location-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  align-items: center;
}

@media (max-width: 768px) {
  .location-grid {
    grid-template-columns: 1fr;
  }
}


Tarea 5: Punto Extra - Rutina en JavaScript para Modo Oscuro

Requerimiento: Desarrollar la lógica en JavaScript para la conmutación de temas (Modo Claro / Modo Oscuro) con guardado del estado en localStorage.

Solución Técnica: Escuchador de eventos (click) que alterna la clase dark-mode en el cuerpo del documento y almacena la preferencia.

const themeToggle = document.getElementById('themeToggle');

themeToggle.addEventListener('click', () => {
    document.body.classList.toggle('dark-mode');
    const isDark = document.body.classList.contains('dark-mode');
    localStorage.setItem('theme', isDark ? 'dark' : 'light');
});

// Carga inicial según preferencia guardada
if (localStorage.getItem('theme') === 'dark') {
    document.body.classList.add('dark-mode');
}


🎯 Conclusión

El registro demuestra la utilización de la IA como un asistente técnico eficiente para la resolución de fragmentos de código específicos y la optimización de la experiencia de usuario, manteniendo la autoría y dirección técnica del proyecto por parte del estudiante.