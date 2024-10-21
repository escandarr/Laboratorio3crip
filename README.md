# Informe Laboratorio 3

Este informe documenta la auditoría de seguridad realizada sobre la implementación de algoritmos de hash aplicados a contraseñas en el sitio web [LinuxQuestions.org](https://www.linuxquestions.org/). La auditoría tiene como objetivo evaluar la robustez de las medidas de seguridad contra ataques de tipo Pass the Hash (PtH) y hacer recomendaciones de mejora.

## Descripción de las actividades

Se realizaron las siguientes actividades durante la auditoría:

1. **Identificación del algoritmo de hash utilizado al registrarse:** Se utilizó la herramienta de desarrollo del navegador para interceptar el tráfico y verificar que el algoritmo MD5 se emplea para procesar la contraseña durante el registro.
   
2. **Identificación del algoritmo de hash al iniciar sesión:** Utilizando BurpSuite, se interceptó la solicitud POST de inicio de sesión, confirmando nuevamente que el algoritmo MD5 se utiliza para enviar el hash de la contraseña al servidor.

3. **Generación del hash desde la consola del navegador:** Se verificó cómo el algoritmo MD5 procesa la contraseña en el lado del cliente usando la función `hex_md5()` en la consola del navegador. Se generó el hash de la contraseña y de una cadena adicional como prueba.

4. **Intercepción del tráfico con BurpSuite:** Se utilizó BurpSuite para interceptar la solicitud POST de inicio de sesión y capturar los hashes generados antes de que fueran enviados al servidor.

5. **Intento de login con modificación del hash:** Se realizó un intento de login con una contraseña incorrecta, interceptando la solicitud para modificar el hash incorrecto por el hash correcto, lo que permitió evaluar la vulnerabilidad del sitio ante ataques de tipo Pass the Hash (PtH).

6. **Políticas de privacidad y seguridad:** Se revisaron las políticas de seguridad del sitio para evaluar las medidas implementadas en la protección de datos de los usuarios y las áreas que podrían mejorarse.

## Herramientas Utilizadas

- **BurpSuite:** Utilizada para interceptar y analizar el tráfico de red durante los procesos de registro e inicio de sesión.
- **Consola del Navegador:** Para generar y verificar el hash MD5 de la contraseña en el lado del cliente.
- **LinuxQuestions.org:** Sitio utilizado para realizar las pruebas y auditorías.

## Enlace a la Política de Privacidad

Para más información sobre la política de privacidad de LinuxQuestions.org, puede consultarse el siguiente [enlace](https://www.linuxquestions.org/linux/privacy.html).

