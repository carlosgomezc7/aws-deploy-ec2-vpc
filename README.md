# Documentación del Proyecto: CTI SOLUCIONES (Soporte TI Pro)

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

## 6. Infraestructura y Despliegue en la Nube (AWS)
El proyecto ha sido desplegado y configurado utilizando diversos servicios e infraestructura de **Amazon Web Services (AWS)** para garantizar alta disponibilidad, seguridad y acceso global.

### 6.1. Servidor de Cómputo (Amazon EC2)
*   **Instancia EC2:** Se levantó una instancia virtual de tipo **t3.micro** (nombre del servidor: `server`) con sistema operativo Linux para hospedar el servidor web de forma continua.
*   **ID de la Instancia:** `i-02c919db642ad7fa9`.
*   **Estado de la Instancia:** `Running` (En ejecución).
*   **Acceso Directo por IP (Levantamiento):** El sitio web está disponible públicamente de manera directa a través de su IP IPv4: **[http://52.14.219.174/](http://52.14.219.174/)**.
*   **DNS / Public IP:** `ec2-52-14-219-174.us-east-2.compute.amazonaws.com`.
*   **Acceso Seguro (SSH):** Configurado para conectarse de forma segura mediante llave privada SSH (`keysf.pem`) utilizando el usuario `ec2-user`:
    ```bash
    ssh -i "keysf.pem" ec2-user@ec2-52-14-219-174.us-east-2.compute.amazonaws.com
    ```

### 6.2. Red y Seguridad (VPC - Virtual Private Cloud)
Para aislar la infraestructura y controlar el tráfico de red, se implementó la siguiente topología de red virtual:
*   **VPC Personalizada:** VPC ID `vpc-02f6fb00901e61180` con un rango de red CIDR de `172.31.0.0/16`.
*   **Subredes (Subnets):** Configuración de subredes para la distribución y el ruteo interno. La subred asociada y activa es `subnet-0d8911ae689f9158e` (rango `172.31.0.0/20`).
*   **Puerta de Enlace (Internet Gateway):** `igw-03737898b2f459c9d` acoplada a la VPC para posibilitar el tráfico bidireccional con Internet.
*   **Tabla de Ruteo (Route Table):** `rtb-0307c2659297a485a` con regla de salida hacia el Internet Gateway (`0.0.0.0/0 -> igw-03737898b2f459c9d`).
*   **Grupo de Seguridad (Security Group):** `launch-wizard-1` (`sg-0e2c6ef8987a7e483`) actuando como firewall virtual a nivel de instancia, permitiendo reglas de entrada (Inbound Rules) específicas:
    *   **HTTP (Puerto 80):** Tráfico web abierto para cualquier origen (`0.0.0.0/0`).
    *   **HTTPS (Puerto 443):** Preparado para tráfico cifrado SSL/TLS (`0.0.0.0/0`).
    *   **SSH (Puerto 22):** Acceso remoto para la administración del servidor (`0.0.0.0/0`).

### 6.3. Almacenamiento y Respaldos (Amazon S3)
*   **Bucket de S3:** `bucket-cti-soluciones`.
*   **Propósito:** Almacenamiento en la nube de los archivos estáticos de producción y de desarrollo del sitio (código HTML, estilos CSS compilados, archivos SCSS de origen, imágenes vectoriales SVG y documentación técnica).
*   **Políticas de Acceso:** Configurado con permisos de lectura pública específicos (`PublicReadGetObject` para la política del bucket `arn:aws:s3:::bucket-cti-soluciones/*`) desactivando la opción de bloqueo de acceso público para servir los recursos directamente si es necesario.

