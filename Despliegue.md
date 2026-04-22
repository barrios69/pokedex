 ##  Informe de Despliegue y Seguridad

 Estrategia de Despliegue
La aplicación ha sido desplegada utilizando una arquitectura de **Static Web Apps** en **Microsoft Azure**. 

### Ciclo de Vida (CI/CD)
Se implementó un flujo de **Integración y Despliegue Continuo**:
1. El código se aloja en **GitHub** con el nombre de usuario **barrios69**
2. Cada `push` a la rama `main` activa un **GitHub Action**.
3. El Action compila el proyecto Angular y sincroniza los artefactos con los servidores de Azure.

##  Implementación de Seguridad
Siguiendo los requerimientos de "Pueblo Paleta Inc.", se configuró un archivo `staticwebapp.config.json` para fortalecer el servidor frente a ataques comunes:

* **Content Security Policy (CSP):** Se restringieron las fuentes de scripts y conexiones solo a dominios confiables (`self`, `pokeapi.co`), mitigando ataques XSS.
* **X-Frame-Options (DENY):** Previene ataques de Clickjacking.
* **Strict-Transport-Security (HSTS):** Fuerza el uso de conexiones seguras HTTPS.
* **X-Content-Type-Options (nosniff):** Evita que el navegador interprete archivos de forma incorrecta.

##  Resultado de Validación
El despliegue fue validado mediante la herramienta **SecurityHeaders.com**, obteniendo una calificación de seguridad grado **A**.
