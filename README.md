# Jurassic World: temas para Kino TV

Un plugin con **tres temas para toda la app**, uno por película, cada uno con su paleta, sus formas, su movimiento, su reproductor y su propio logo. Funcionan en el celular y en la TV.

Es un plugin **solo de temas**: son datos en el manifiesto, no corre código, no usa la red y no pide capacidades.

## Requisitos

- Kino **0.9.81** o posterior (`apiVersion` 18).
- Los bordes (`colors.border`, `shape.*Border`) se dibujan desde Kino **0.9.82**. En 0.9.81 los temas se ven igual, pero sin bordes.

## Los tres temas

| | JW1 · Isla Nublar | JW2 · Reino Caído | JW3 · Dominion |
|---|---|---|---|
| Ambiente | Parque abierto, selva y tecnología | Volcán en erupción y mansión | Biosyn: acero, ámbar y laboratorio |
| Acento | Verde agua `#2EE6C8` | Lava `#FF4D1A` | Ámbar `#FFB81C` |
| Fondo | Verde selva profundo | Negro rojizo con brasa abajo | Azul acero casi negro |
| Formas | Muy redondeadas (18–28) | Medias (8–12) con bordes de brasa | Casi rectas (2–4) con bordes de acero |
| Reproductor | Botones circulares, play 1,4× | Botones redondeados, barra gruesa 1,4× | Botones cuadrados, tamaño contenido |
| Movimiento | Suave: fundido de 400 ms | Dramático: zoom de foco 1,1 | Seco: fundido de 150 ms, sin deriva |
| Experiencia sugerida | Completa | Completa | Ligera (sin sombras ni efectos) |
| Logo | **NUBLAR** + esfera | **FALLEN** + volcán | **BIOSYN** + hexágono de ámbar |

Los logos son vectores propios (letras de bloque con sombra en capas y una marca cuadrada para el riel cerrado del TV). No reproducen los logotipos oficiales de las películas.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `kino-plugin.json` | Manifiesto con los tres temas (`isla-nublar`, `fallen-kingdom`, `dominion`) |
| `plugin.js` | Vacío a propósito (`export {};`): Kino lo exige pero no lo llama |
| `icon.png` | Icono 512×512: tres garras, una por tema, con los colores de cada uno |
| `README.md` | Este archivo |

## Instalación

1. Sube los cuatro archivos a la raíz de un repositorio de GitHub.
2. En Kino, instala el plugin con su dirección `owner/repo`.
3. Elige un tema en **Ajustes ▸ Apariencia**. Kino preguntará si quieres usar también la experiencia completa o ligera que sugiere cada tema; nada cambia sin tu sí.

No cambies los `id` de los temas después de publicar: de ellos cuelgan la elección y los ajustes de cada persona.

## Personalizar (Ajustes ▸ Apariencia ▸ Personalizar)

En los tres: color de acento (tres muestras compatibles con control remoto), redondeo de tarjetas, tamaño del texto (0,95–1,2) y fondo.

## Legibilidad

Los pares de color cumplen las protecciones de Kino: fondo oscuro, texto 4,5:1, acento sobre fondo 3:1 y `onAccent` sobre acento 4,5:1. Las muestras de acento también las cumplen.

## Probar antes de publicar

```
node sdk/validate.mjs .
```

Debe pasar sin advertencias en celular ni en TV. Los colores no se ven con el kit: míralos en la vista previa de **Ajustes ▸ Apariencia**.

## Notas

- El manifiesto pesa unos 14 KB; el máximo es 16 KB, así que hay poco margen para agregar más temas con logo.
- `entry` e `icon` van sin `./` al principio, como pide Kino.
- Proyecto de fans: Jurassic World pertenece a sus dueños; este tema no es oficial.
