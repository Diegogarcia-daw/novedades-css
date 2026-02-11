# Novedades de CSS: :has() & Popover API

Este repositorio contiene una demostración práctica de dos de las características más potentes y modernas del desarrollo web actual: el pseudo-clase **`:has()`** (también conocido como "Selector Padre") y la **Popover API** nativa.

El objetivo de este proyecto es demostrar cómo podemos crear interfaces interactivas y accesibles utilizando **solo HTML y CSS**, reduciendo drásticamente la dependencia de JavaScript para la lógica visual.

## 📋 Contenido

El proyecto se divide en dos ejemplos clave:

1.  **Card Interactiva con `:has()`**: Una tarjeta que cambia su diseño completo (borde, fondo, sombra) basándose en el estado de un `checkbox` hijo.
2.  **Menú Nativo con Popover**: Un elemento flotante que utiliza la nueva API del navegador para gestionarse sin `z-index` ni scripts de cierre manual.

## 🔍 Explicación del Código

### 1. El Selector Padre (`:has`)

El requisito era crear una tarjeta que reaccionara a su contenido. Tradicionalmente, esto requería JavaScript para detectar el cambio en el `input` y añadir una clase al padre.

Con `:has()`, invertimos la lógica de cascada:

```css
/* Selecciona la tarjeta (.card) SOLO SI contiene un input marcado */
.card:has(input:checked) {
  border-color: #6366f1;
  background-color: #eef2ff;
  box-shadow: 0 10px 25px rgba(99, 102, 241, 0.25);
  transform: translateY(-5px);
}
```
2. Atributo Popover
Para mostrar información superpuesta (Top Layer) con funcionalidad de "Light Dismiss" (cerrar al hacer clic fuera o presionar ESC), utilizamos la API estándar:

HTML:
<button popovertarget="mi-info">Ver Info</button>

<div id="mi-info" popover>
  <p>Este es un elemento nativo. Cierra haciendo clic fuera.</p>
</div>

Estas características forman parte de Baseline 2024 y son soportadas por las últimas versiones de todos los navegadores modernos ("Evergreen Browsers"):

✅ Google Chrome

✅ Microsoft Edge

✅ Mozilla Firefox

✅ Safari / iOS
