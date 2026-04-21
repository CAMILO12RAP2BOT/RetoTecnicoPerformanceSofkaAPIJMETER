# Reto Técnico de Carga: Login API - Sofka

Este repositorio contiene la solución automatizada para las pruebas de rendimiento del endpoint de autenticación de *
*FakeStoreAPI**. La implementación utiliza **JMETER** para validar la capacidad de respuesta y estabilidad del sistema
bajo
condiciones de carga controlada.

## Perfil del Proyecto

* **Herramienta:** JMETER (Load Testing Tool).
* **Lenguaje:** Java superior 8.
* **Objetivo:** Evaluar el cumplimiento de los acuerdos de nivel de servicio (SLA) en el proceso de login.

## Estructura del Directorio

```text
.
├── datos/
│   └── data.csv                                                # Credenciales de prueba (user, passwd)
└── scripts/ 
    └──Test Plan JMETER Reto Tecnico Sofka Performance.jmx      # Script de automatización en JMETER
```

### Configuración del Escenario de Carga

| Parámetro          | Valor  | Descripción                                                                            |
|--------------------|--------|----------------------------------------------------------------------------------------|
| Target Throughput  | 1200.0 | Equivale a 20 TPS. JMeter lo calcula como muestras por minuto (20 p/s × 60s).          |
| Duration (seconds) | 60     | Tiempo total en segundos que el Thread Group estará activo enviando peticiones.        |
| Ramp-up Period     | 5      | Tiempo en que JMeter tarda en subir de 0 a 50 hilos. Equivale a la preparación de VUs. |
| Number of Threads  | 50     | Cantidad total de "Hilos" (usuarios virtuales) máximos configurados en el grupo.       |

### Umbrales de Calidad (Thresholds)

La prueba se marca como exitosa si se cumplen los siguientes criterios técnicos:

- **Duration Assertion:** El tiempo máximo (max) de respuesta debe ser <= 1500ms.
- **Response Assertion:** La tasa de errores debe ser inferior al 3% (rate < 0.03).

## Comando de Ejecución

Ejecuta el siguiente comando desde la carpeta donde se encuentra el script:

```
jmeter -n -t ".\Test Plan JMETER Reto Tecnico Sofka Performance.jmx" -l resultados.jtl -e -o .\reporte_html
```
**Nota: Configurar variables de entorno en el sistema** 

### Reportes y Resultados

El script incluye un comando que genera el reporte HMTL de JMETER

**Desarrollado por:** Camilo Andres Amaya Granados
**Rol:**

Analista de calidad manual/ Automatizador de pruebas/ Estudiante de Especialización en Big Data

**Fecha de actualización:** 21 de Abril 2026