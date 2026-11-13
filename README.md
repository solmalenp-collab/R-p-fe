# Rüpüfe · Senderos de Neuquén

Guía web de senderos de la provincia de Neuquén.

*Rüpüfe* significa "caminante de los caminos" en mapudungun.
Proyecto del programa **Frontend Energía Digital 2026** (Fundación YPF · Jump Educación).

### Páginas

| Archivo | Contenido |
|---|---|
| `index.html` | Portada, senderos destacados y beneficios de la guía |
| `senderos.html` | Grilla con los 5 senderos |
| `senderos/lanin.html` | Detalle completo de un sendero  |
| `senderos/arrayanes.html` | Detalle completo de un sendero  |
| `senderos/domuyo.html` | Detalle completo de un sendero  |
| `senderos/atravesada.html` | Detalle completo de un sendero  |
| `senderos/copahue.html` | Detalle completo de un sendero  |
| `senderos/tromen.html` | Detalle completo de un sendero  |
| `senderos/costanera.html` | Detalle completo de un sendero  |
| `senderos/chachin.html` | Detalle completo de un sendero  |
| `senderos/Belvedere.html` | Detalle completo de un sendero  |
| `nosotros.html` | Historia y valores del proyecto |
| `contacto.html` | Formulario de contacto |

### Estructura

```
├── index.html
├── senderos.html
├── nosotros.html
├── contacto.html
├── senderos/
│   └── lanin.html
│   └── arrayanes.html
│   └── domuyo.html
│   └── atravesada.html
│   └── copahue.html
│   └── tromen.html
│   └── costanera.html
│   └── chachin.html
│   └── belvedere.html
├── css/
│   └── styles.css
└── img/
│   └── lanin
│   └── arrayanes
│   └── domuyo
│   └── atravesada
│   └── copahue
│   └── tromen
│   └── costanera
│   └── chachin
│   └── belvedere
```

### Qué se aplicó

- **HTML semántico:** `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`, listas, formulario y `dl` para la ficha técnica.
- **Box model** con `box-sizing: border-box`, márgenes y padding consistentes.
- **Flexbox:** header, navegación, botones, tarjetas y formulario.
- **Grid:** grilla de tarjetas, layout del sendero, galería y valores.
- **Media queries:** 3 tamaños (celular, tablet desde 768px y escritorio desde 1024px).
- **Pseudo-clases:** `:hover`, `:focus`, `:focus-visible` y `:user-invalid` en el formulario.
- **Accesibilidad:** `alt` en imágenes, `aria-current` en la página activa, `label` en todos los campos y respeto por `prefers-reduced-motion`.
- **Extra:** Google Fonts (Montserrat y Open Sans).
**
# ##tener muy en cuenta y controlar##**

- controlar las fotos reales .
- Verificar los datos de cada sendero con Parques Nacionales.

**## Mapa de la provincia (HTML + CSS)**

En la portada hay un dibujo simple de Neuquén (`img/neuquen.svg`) con un círculo y foto por cada sendero:

- **Al pasar el mouse** (o con Tab desde el teclado) aparece la ficha: nombre, zona, dificultad y duración.
- **Al hacer clic** lleva a la página del sendero.
- El borde de cada foto indica la dificultad: verde (baja), amarillo (media), naranja (alta) y rojo (muy alta).

### Cómo se ubica cada punto

El dibujo cubre un rectángulo conocido de coordenadas, --x --y
```
En el HTML cada punto lleva su posición: `style="--x: 42.86%; --y: 63.5%;"`, y el CSS lo coloca con `position: absolute; left: var(--x); top: var(--y);`. Como son porcentajes, los puntos quedan en su lugar en cualquier tamaño de pantalla.
Para que las medida sean exactas utilice css modificandolo en linea y de esta manera ver en el momento la ubicacion del punto

Como los senderos estában muy cerca entre sí en el sur de la provincia, cada foto se muestra un poco corrida y una línea punteada en el dibujo marca el lugar exacto.

El contorno de la provincia, ríos y lagos principales sale de [Natural Earth](https://www.naturalearthdata.com) (dominio público), simplificado. Los lagos Lácar, Huechulafquen, Lolog y Aluminé están dibujados de forma aproximada.

JS

Las páginas de `senderos/` se va a remplazar por un único `sendero.html?id=...` que lee los datos desde `data/senderos.json`. Ese JSON ya tiene la ubicación (`lat`, `lng`) de cada sendero, así que JavaScript también puede calcular los porcentajes y armar los puntos del mapa.
