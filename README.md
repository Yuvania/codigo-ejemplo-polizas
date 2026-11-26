# Código de ejemplo de pólizas

Repositorio de código Python, con datos completamente ficticios, que representa un sistema de pólizas de seguros. Es el código que revisa el **Asesor Técnico** del proyecto [asistente-multiagente-historias-usuario](https://github.com/Yuvania/asistente-multiagente-historias-usuario) para determinar qué otras partes del sistema afecta un cambio descrito en una historia de usuario.

## Propósito

Cuando una historia de usuario modifica un dato (por ejemplo, que el teléfono del cliente deje de ser obligatorio), el cambio rara vez se limita a la pantalla donde se pidió. Este repositorio reproduce esa situación: varios módulos reutilizan los mismos datos del cliente, de modo que un cambio en uno afecta a la pantalla, los avisos, los reportes y las cargas masivas. Sirve para evaluar si el Asesor Técnico encuentra todos los lugares afectados, incluidos los que la historia no menciona.

## Alcance y restricciones

- **Datos ficticios:** claves con prefijo `DEMO-`, montos didácticos y operaciones en memoria. No contiene datos personales.
- **Sin integraciones:** no se conecta con aseguradoras, bancos, bases de datos ni servicios externos. La fórmula de prima es ilustrativa y no constituye una tarifa actuarial.
- **Solo lectura:** el Asesor Técnico descarga una copia superficial y lee únicamente los archivos `.py` y `.md` como texto; el código no se importa ni se ejecuta.

## Estructura

| Módulo | Responsabilidad |
|---|---|
| `modelos.py` | Tipos de póliza, cobertura, pago y propuesta de renovación |
| `servicios/validaciones.py` | Validación del prefijo, el producto, las fechas y la prima |
| `servicios/polizas.py` | Creación y activación de una póliza en memoria |
| `servicios/coberturas.py` | Catálogo y asociación de coberturas |
| `servicios/primas.py` | Cálculo ilustrativo y redondeo de la prima |
| `servicios/renovaciones.py` | Propuesta de nueva fecha e importe de renovación |
| `servicios/pagos.py` | Recibo de pago simulado |
| `clientes/` | Modelo del cliente y pantalla «Datos del cliente» con sus validaciones |
| `notificaciones/` | Avisos de bienvenida por correo electrónico y mensaje de texto |
| `reportes/` | Exportación «Clientes activos» |
| `cargas/` | Carga masiva de clientes por archivo |

El archivo [`mapa_dependencias.md`](mapa_dependencias.md) resume los módulos, sus dependencias y los procesos críticos. Es el punto de partida del Asesor Técnico.

## Escenarios de evaluación

Los casos con los que se evalúa al Asesor Técnico (teléfono opcional, cambio de formato de fecha y correo secundario), con los módulos que debe encontrar en cada uno, están descritos en la [guía de evaluación del proyecto principal](https://github.com/Yuvania/asistente-multiagente-historias-usuario/blob/main/docs/evaluacion-asesor-tecnico.md).

## Uso en el proyecto principal

El proyecto principal descarga este repositorio al arrancar, según la variable de entorno:

```text
ASESOR_REPOSITORIO_URL=https://github.com/Yuvania/codigo-ejemplo-polizas.git
```

Las rutas de importación (`ejemplos.polizas_demo`) corresponden a la copia de respaldo incluida en el proyecto principal y se conservan para que ambas versiones coincidan.

## Autoría

Elaborado por Yuvania Castillo para el curso de Inteligencia Artificial de Cenfotec.
