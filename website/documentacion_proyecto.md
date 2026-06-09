# Documentación del Proyecto: Soporte TI Pro

## 1. Propósito del Sitio
Este sitio web ha sido diseñado como una plataforma informativa para una empresa de **Soporte Técnico y Servicios Gestionados de TI**. El objetivo principal es proyectar profesionalismo, confianza y eficiencia técnica, permitiendo a los clientes potenciales conocer la oferta de servicios, la trayectoria de la empresa y facilitar un canal de contacto directo.

## 2. Estructura del Sitio
El sitio se compone de cinco páginas interconectadas, cada una con una función específica:
*   **Inicio (index.html):** Página de aterrizaje con un banner de impacto (Hero), resumen de servicios principales y planes destacados.
*   **Sobre Nosotros (nosotros.html):** Detalla la historia, misión, valores y estadísticas clave de la organización para generar confianza.
*   **Soporte (soporte.html):** Centro de ayuda que desglosa los recursos técnicos, herramientas remotas y tablas comparativas de planes de soporte.
*   **Preguntas Frecuentes (preguntas-frecuentes.html):** Sección de FAQ para resolver dudas comunes sobre niveles de servicio (SLA) y seguridad.
*   **Contacto (contacto.html):** Formulario estructurado para la captación de leads y datos de ubicación física/digital.

## 3. Justificación del Diseño
*   **Paleta de Colores:** 
    *   **Azul (#0270D7):** Utilizado como color primario para evocar seguridad, integridad y tecnología.
    *   **Oscuros (#15181D, #1D2026):** Los fondos oscuros (Dark Mode) proporcionan una estética moderna, reducen la fatiga visual y resaltan los elementos interactivos.
*   **Tipografía:** Se implementó **IBM Plex Sans**. Es una fuente diseñada específicamente para contextos técnicos, lo que refuerza la identidad de una empresa de ingeniería.
*   **Iconografía:** Uso de gráficos vectoriales (SVG) que garantizan nitidez en cualquier resolución y mantienen el sitio ligero para una carga rápida.
*   **Organización Visual:** Se utilizó un diseño basado en tarjetas (Cards) y rejillas (Grids) para facilitar la lectura escaneable de la información técnica.

## 4. Organización de la Carpeta de Archivos
El proyecto sigue una estructura profesional y escalable:

*   **/ (Raíz):** Contiene los archivos HTML principales del sitio.
*   **/dist:** Archivos listos para producción.
    *   `css/`: Contiene el archivo `style.css` final compilado.
    *   `images/`: Almacena logos, iconos de características y recursos gráficos en formato SVG.
*   **/src:** Archivos de origen para desarrollo.
    *   `scss/`: Contiene la arquitectura modular de estilos (Variables, Mixins, Layouts, Componentes).
    *   `js/`: Archorio para scripts (actualmente optimizado para ser un sitio estático puro).
*   **/others:** Carpeta de recursos adicionales (Documentación del proyecto).

## 5. Detalles Técnicos
*   **HTML5 & CSS3:** Uso de etiquetas semánticas y Flexbox/Grid para el posicionamiento.
*   **Arquitectura CSS (Sass):** Se utilizó el preprocesador Sass con una metodología modular (similares a SMACSS), permitiendo que el mantenimiento de colores y tipografías sea centralizado mediante variables globales.
*   **Diseño Responsivo:** El sitio está optimizado para dispositivos móviles y escritorio mediante Media Queries integrados en la arquitectura de estilos.

---
*Documentación preparada para el entregable de diseño y organización de sitios web estáticos.*