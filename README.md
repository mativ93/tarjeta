# Tarjeta virtual — Matias Verde

## Qué hay acá

| Archivo | Qué es |
|---|---|
| `index.html` | La tarjeta como página web (con botones que funcionan) |
| `tarjeta.png` | La tarjeta como imagen (1040 × 1520) |
| `matias-verde.vcf` | Contacto para guardar en la agenda del teléfono |
| `README.md` | Este archivo |

---

## Tres formas de compartirla

### 1. Como link (la buena)

La tarjeta es una página, no una foto: para compartirla hay que publicarla y mandar la URL.

1. Crear un repo público en GitHub, por ejemplo `tarjeta`.
2. Subir el contenido de esta carpeta a la raíz.
3. Settings → Pages → Source: *Deploy from a branch* → Branch `main`, carpeta `/ (root)`.
4. Queda en `https://TU-USUARIO.github.io/tarjeta/`.

Ese link se pega en WhatsApp y la otra persona abre la tarjeta con los botones activos
(WhatsApp, email, guardar contacto).

Para que el link muestre miniatura en WhatsApp: subir una imagen 1200×630 como `preview.jpg`
y descomentar la etiqueta `og:image` en el `<head>`, con la URL absoluta.

### 2. Como imagen

Adjuntar `tarjeta.png` en el chat (clip → Fotos). Se ve al instante, sin abrir nada,
pero no es clickeable. Conviene mandarla junto con el link.

Se puede regenerar con Chrome:

```
chrome --headless=new --force-device-scale-factor=2 --window-size=520,760 ^
  --screenshot="tarjeta.png" "index.html?img"
```

(En el modo `?img` se oculta el botón "Copiar enlace" y se muestra el número de WhatsApp.)

### 3. Como contacto

Adjuntar `matias-verde.vcf` (clip → Documento). A la otra persona le aparece
"Agregar contacto" y queda en su agenda sin escribir nada.

---

## Qué editar

- Nombre, rol y descripción: dentro de `<main class="card">`.
- Teléfono: en tres lugares — link `tel:`, texto visible y link `wa.me`.
  Formato internacional: `+54 9 353 412-8663` / `5493534128663`.
- Ubicación: fila con el ícono de pin (Villa María, Córdoba).
- Color de acento: variable `--accent` en el `<style>`.
- Si cambia el teléfono o el email, actualizar también `matias-verde.vcf` y regenerar `tarjeta.png`.
