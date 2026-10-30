# ECOVOLT · Prototipo digital

Prototipo de aplicación (una sola página, sin dependencias) para el proyecto **ECOVOLT**: sistema de enfriamiento residencial con energía solar y tubos subterráneos. Florencia, Caquetá, Colombia.

## Cómo abrirlo

- **En computador:** abre `index.html` con doble clic (Chrome, Edge o Firefox).
- **En celular (Android):** envía el archivo como **documento**, descárgalo y ábrelo con **Chrome**. No lo abras desde la vista previa de WhatsApp, Drive o Telegram: esas vistas no ejecutan JavaScript y el prototipo se ve vacío o roto.
- **Desde la red local:** si sirves esta carpeta en tu Wi-Fi (por ejemplo `http://192.168.1.11:8080/index.html`), ábrela desde Chrome en el celular. Si no carga, Windows está bloqueando el puerto en el firewall.
- No necesita instalación. Solo la tipografía se descarga de Google Fonts (si no hay internet se usa la fuente del sistema).

Si algo falla, la página muestra un aviso rojo con el detalle en lugar de quedarse en blanco.

## Acceso

| Opción | Datos |
|---|---|
| Cuenta demo | botón **Usar cuenta demo** (Camila Restrepo) |
| Crear cuenta | pestaña **Crear cuenta** (nombre + correo + contraseña de 4+ caracteres) |
| Invitado | enlace **Entrar como invitado** |
| Ingresar | cualquier correo válido + contraseña de 4+ caracteres |

La sesión se guarda en `localStorage`. Si el navegador bloquea el almacenamiento, el login sigue funcionando en memoria.

## Pantallas (10)

1. **Inicio** — qué hace el producto, diagrama del sistema, accesos rápidos.
2. **Simulador** — calcula temperatura de salida, efectividad, consumo y ahorro.
3. **Problema** — calor, humedad, costo del aire acondicionado y comparativo.
4. **Solución** — paneles, ventilador y tubos; conexión con el problema.
5. **Cómo funciona** — 4 pasos interactivos (seleccionables).
6. **Beneficios** — ahorro, comodidad, ambiente y adaptación.
7. **Materiales y pruebas** — insumos, protocolo, precauciones y requisitos.
8. **Modelo de negocio** — producto, clientes, costos e ingresos.
9. **Identidad** — logo, paleta, tono y eslogan.
10. **Contacto** — formulario validado, perfil de la sesión y confirmación.

## Interacciones que funcionan

- Login / registro / invitado / cerrar sesión.
- Navegación por menú lateral, barra móvil y botón atrás del navegador (rutas `#/pantalla`).
- Simulador con 4 controles: recalcula temperatura, consumo y ahorro; avisa riesgos por humedad o tubo corto.
- **Guardar en mi solicitud**: pasa los datos de la simulación al formulario de contacto.
- Pasos 1–4 de «Cómo funciona» con contenido dinámico.
- Formulario de contacto con validación y confirmación (envío **simulado**, sin backend).
- Guía del prototipo (botón del encabezado) con el mapa de la rúbrica.
- Animaciones del diagrama (sol, ventilador, flujo de aire) e interruptor **Animaciones** en el encabezado; la preferencia se guarda y no depende de la configuración de Windows.

## Relación con la actividad

| Requisito | Dónde se cumple |
|---|---|
| Se entiende el propósito | Inicio + eslogan + descripción del sistema |
| Usuario identificado | Login con nombre/correo reutilizado en contacto |
| La solución responde al problema | Problema → Solución → Cómo funciona |
| Mínimo 4 botones con función | Navegación, login, simulador, guardar, enviar, pasos |
| Login y pantallas de login | Ingresar, crear cuenta, demo, invitado, recuperación |
| Cada elemento tiene una función | Controles que calculan, pasos que cambian, formularios que validan |
| Pantallas ordenadas | 10 pantallas agrupadas en 4 bloques del menú |
| Textos legibles / imágenes pertinentes | Tipografía amplia, diagrama SVG del sistema, iconografía propia |
| Navegación completa | Menú, barra móvil, historial, botones de avance |
| Precauciones y requisitos | «¿Qué pasa cuando…?» + requisitos del usuario |

## Límites (importante)

- Los cálculos son **estimaciones educativas** (suelo a 24 °C, tarifa de $750/kWh); no son mediciones.
- El rendimiento real **no está comprobado**: no garantiza el frío de un aire acondicionado.
- El envío del formulario **no sale del navegador**: es una simulación del prototipo.

## Dónde editar

- Colores y medidas: variables CSS en `:root`.
- Pasos del sistema: arreglo `STEPS` en el `<script>`.
- Modelo del simulador: función `updateSim()`.
- Textos: directamente en cada `<section class="screen">`.
