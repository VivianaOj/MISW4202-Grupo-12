# Experimento Seguridad Arquitectura ABC Jobs

Video

## Integrantes

- Camilo Ramírez Restrepo
- Laura Daniela Molina Villar
- Leidy Viviana Osorio Jiménez
- Tim Ulf Pambor 

# Comandos para poder ejecutar el experimento:


## Propósito del experimento
El objetivo principal de este experimento es evaluar la seguridad del microservicio AdminContrato mediante un sistema de autenticación y autorización implementado a través de un API Gateway y un microservicio Autorizador. Específicamente, se busca verificar si el sistema puede validar correctamente las solicitudes de los usuarios, emitir tokens de acceso solo a usuarios autorizados y controlar el acceso a un microservicio AdminContrato que gestiona (ver/editar) contratos.​

## Resultados esperados
- Verificación exitosa de autenticación: Los usuarios que proporcionen credenciales válidas deben recibir un token de acceso. ​
- Control de acceso efectivo: Solo los usuarios autorizados deberían poder acceder a contratos y realizar operaciones de escritura. ​
- Respuestas adecuadas: ​
   - Si las credenciales son correctas se envía el token, si no un mensaje de error.​
   - Si el Autorizador verifica el rol del usuario y además que el token esté activo, envía a AdminContrato por medio de API Gateway la información del usuario (rol, id usuario). De lo contrario envía un código de acceso denegado​
   - Si AdminContrato verifica que el usuario que intenta hacer la edición del contrato fue la que creó el mismo, envía un mensaje de confirmación a AppWeb, por medio del API Gateway. De lo contrario envía un código de acceso denegado.
​
## Recursos requeridos
Cuatro computadores personales con Docker y Docker compose instalados, además deben contar con una licencia de un IDE para programación en Python.​
Framework: Flask.​

## Elementos de arquitectura involucrados
 - ASR: En una operación normal el componente Autorizador junto con AdminContrato deben garantizar que la edición de un contrato solo sea realizada por usuarios autorizados, esto el 100% de las veces.​
 - Elementos de la arquitectura afectados: Microservicio AdminContrato, Microservicio Autorizador, ApiGateway, y AppWeb.​
 - Vistas donde se encuentran elementos: Vista funcional, de despliegue, de información y de concurrencia.​
 - Punto de sensibilidad que se desean probar: El microservicio Autorizador, ya que será el encargado de generar los tokens, y verificar roles. ​

## Esfuerzo estimado
Se estima que el experimento requerirá alrededor de 48 horas (12 horas/hombre) con un sprint de una semana, para la configuración, desarrollo, pruebas y análisis de resultados. ​
