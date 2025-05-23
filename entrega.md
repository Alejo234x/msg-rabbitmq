Iimplementar un sistema de gestión de logs de estaciones meteorológicas descrito en este caso de estudio. 
Debe entregar un prototipo funcional que contemple los siguientes elementos y considere las restricciones y usos potenciales.

## Elementos a tener en cuenta:

### Productores de datos (Producers):
- [x] Servicio en Python que simule o reciba datos de estaciones (JSON).
- [x] Debe publicar a un exchange de RabbitMQ con mensajes durables.

### Broker de mensajería:
- [x] Configuración de RabbitMQ con colas durables y bindings adecuados.
- [x] Incluir dashboard de administración.

### Consumidores (Consumers): 
Microservicio en Python que:
- [ ] Procesa los mensajes con ack manual.
- [x] Persiste en PostgreSQL (tabla weather_logs).
- [x] Valida rangos de valores y gestiona errores.

### Base de datos:
- [x] Definir esquema en PostgreSQL.
- [x] Manejar conexiones seguras y reconexiones automáticas.

### Docker y orquestación:
- [x] Contenedores para RabbitMQ, PostgreSQL, productores y consumidores.
- [x] Archivo docker-compose.yml que garantice arranque ordenado y reinicios automáticos.

### Logs y monitoreo:
- [ ] Incluir registros de eventos en cada componente y métricas de rendimiento. 
- [ ] Proponer uso de Prometheus/Grafana si el tiempo lo permite.

## Restricciones técnicas:

- [x] Python 3.13+ y librerías estables (pika, psycopg2).
- [x] Mensajes marcados como persistent para evitar pérdida.
- [ ] Consumo con prefetch_count=1 para procesamiento ordenado.
- [x] Bases de datos y colas deben ser stateful y persistentes en volúmenes Docker.
- [ ] Seguir buenas prácticas de código, documentación y manejo de excepciones.

## Posibles usos y extensiones:

- [ ] Servicio de alertas en tiempo real si un valor supera umbrales definidos.
- [ ] API REST para consulta de logs históricos y generación de reportes.
- [ ] Integración con paneles de visualización (Grafana) para dashboards en tiempo real.
- [ ] Escalabilidad horizontal: despliegue múltiple de consumidores según carga.

## Entregables esperados:

- [ ] Repositorio Git con código y README.md detallado.
- [ ] Video demostrativo publicado en el foro.
- [ ] Esquema visual del diseño en la documentación
- [x] docker-compose.yml y configuración de volúmenes.
- [x] Scripts de inicialización de la base de datos.
- Documentación de uso y pruebas de validación.

