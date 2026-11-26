# Código de ejemplo de pólizas

Repositorio **ficticio** de código Python que revisa el Agente Asesor Técnico del proyecto
*Historias de Usuario* (curso de IA, Cenfotec). Representa "el sistema" sobre el que se
redactan las historias: alta, coberturas, prima, renovación, pagos y validaciones de pólizas, y un
registro de clientes cuyos campos se reutilizan en varios módulos (pantalla, avisos, exportación y carga).

- Todo es didáctico: claves `DEMO-`, montos de ejemplo y operaciones en memoria.
- No contiene datos personales ni se integra con aseguradoras, bancos, bases de datos ni
  servicios reales. La fórmula de prima es ilustrativa.
- El Asesor Técnico lo lee **solo como texto** (archivos `.py` y `.md`), sin importarlo ni
  ejecutarlo. Empieza por `mapa_dependencias.md`, que resume módulos y dependencias.

Estructura:

| Archivo | Responsabilidad |
|---|---|
| `modelos.py` | Tipos de póliza, cobertura, pago y propuesta de renovación |
| `servicios/validaciones.py` | Prefijo demo, producto, fechas y prima no negativa |
| `servicios/polizas.py` | Crear y activar una póliza en memoria |
| `servicios/coberturas.py` | Catálogo demo y asociación de coberturas |
| `servicios/primas.py` | Cálculo ilustrativo y redondeo de prima |
| `servicios/renovaciones.py` | Propuesta de nueva fecha e importe |
| `servicios/pagos.py` | Recibo de pago simulado |
| `clientes/` | Datos del cliente y pantalla «Datos del cliente» |
| `notificaciones/` | Avisos de bienvenida por correo y mensaje de texto |
| `reportes/` | Exportación «Clientes activos» |
| `cargas/` | Carga masiva de clientes por archivo |
