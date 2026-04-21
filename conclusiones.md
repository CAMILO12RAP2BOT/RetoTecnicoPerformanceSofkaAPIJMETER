# Conclusiones de la Prueba de Carga - Reto Sofka

1. Cumplimiento de carga: Se alcanzó exitosamente la tasa de 20 TPS (1200 RPM) utilizando un Constant Throughput Timer, manteniendo una inyección de tráfico estable durante toda la prueba. 
2. Estabilidad del servicio: La tasa de error se mantuvo en menos 3.00%, cumpliendo estrictamente con el umbral del 3% máximo permitido para el flujo de autenticación. 
3. Rendimiento de respuesta: El tiempo máximo de respuesta fue inferior a 1500 ms, validando que la API de FakeStore soporta la concurrencia bajo los estándares de calidad exigidos. 
4. Validación de datos: El uso de CSV Data Set Config permitió una prueba realista con múltiples credenciales, asegurando que el endpoint procesa correctamente diferentes usuarios dinámicos.
5. Eficacia de aserciones: Las aserciones de respuesta y JSON confirmaron la integridad de las respuestas (HTTP 201) y la generación correcta de tokens de seguridad en cada iteración.