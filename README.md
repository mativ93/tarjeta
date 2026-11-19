# Tarjeta virtual — Matias Verde

## Qué hay acá

| Archivo | Qué es |
|---|---|
| `index.html` | La tarjeta como página web (botones que funcionan) |
| `tarjeta.pdf` | **La tarjeta como PDF: se manda como documento y los botones se tocan** |
| `tarjeta.png` | La tarjeta como imagen vertical (1040 × 1720), para mandar como foto |
| `preview.jpg` | Imagen horizontal (1200 × 630) que usa WhatsApp en la vista previa del link |
| `preview.html` | Fuente de `preview.jpg`. No se comparte |
| `matias-verde.vcf` | Contacto para guardar en la agenda del teléfono |
| `README.md` | Este archivo |

Publicada en: `https://mativ93.github.io/tarjeta/`

---

## La diferencia importante

- **PDF** → se manda como documento, no es un link, y los botones de WhatsApp, email y
  teléfono funcionan al tocarlos dentro del visor.
- **Link** → WhatsApp lo muestra como una tarjeta con imagen, título y descripción.
  Toda la tarjeta es tocable, pero muestra la URL.
- **Imagen (`tarjeta.png`)** → se ve como foto. No se puede tocar.

Para mandar la tarjeta sin link y con botones que funcionen: el PDF.

---

## Cómo se comparte

**Link.** Pegar `https://mativ93.github.io/tarjeta/` en el chat. WhatsApp lo convierte
en la vista previa con `preview.jpg`, y al tocarla se abre la página.

**Foto.** Adjuntar `tarjeta.png` (clip → Fotos). Sirve para mostrarla sin abrir nada.
No es tocable; conviene mandarla junto con el link.

**Contacto.** Adjuntar `matias-verde.vcf` (clip → Documento). Aparece "Agregar contacto"
y queda en la agenda con teléfono, mail y empresa.

> Si WhatsApp muestra una versión vieja de la vista previa, está usando caché.
> Agregar `?v=2` al final del link para forzarla.

---

## Qué editar

- Nombre, rol y descripción: dentro de `<main class="card">`.
- Teléfono: en tres lugares — link `tel:`, texto visible y link `wa.me`.
  Formato internacional: `+54 9 353 412-8663` / `5493534128663`.
- Mensaje precargado de WhatsApp: parámetro `text=` del link `wa.me`.
- Ubicación: fila con el ícono de pin.
- Color de acento: variable `--accent` en el `<style>`.

Después de cambiar teléfono, email o textos hay que regenerar `tarjeta.png` y `preview.jpg`,
y actualizar `matias-verde.vcf`.

## Regenerar las imágenes

```
chrome --headless=new --force-device-scale-factor=2 --window-size=520,860 ^
  --screenshot="tarjeta.png" "index.html?img"

chrome --headless=new --window-size=1200,630 ^
  --screenshot="preview.png" "preview.html"
```

`preview.png` se convierte a JPG (calidad 88) antes de subirlo como `preview.jpg`.
