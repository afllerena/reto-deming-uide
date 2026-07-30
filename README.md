# Reto Deming · Automotive Legends UIDE

Aplicación web interactiva para pantalla táctil del **Spot 04 – Edward Deming** de la Open House de Ingeniería Automotriz de la Universidad Internacional del Ecuador (UIDE).

El visitante asume el rol de gerente, analiza datos reales en un gráfico de control, detecta la anomalía y toma tres decisiones que mueven cuatro indicadores en vivo (Calidad, Costos, Reputación y Clientes). Al final recibe un puntaje de gestión de 0 a 100.

Casos incluidos: Toyota y el Premio Deming (1965), el interruptor de encendido de General Motors, y Detroit frente a Japón (1950).

---

## Estructura

```
index.html              La aplicación completa (HTML + CSS + JS, sin dependencias)
manifest.webmanifest    Permite instalarla como app en pantalla completa (Android)
icon.svg                Ícono de la app
```

No requiere instalación, servidor ni conexión a internet (las fuentes cargan desde internet, pero hay respaldo del sistema si no hay red).

---

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub, por ejemplo `reto-deming-uide`, marcado como **Public**.
2. Sube los tres archivos a la raíz del repositorio (`index.html`, `manifest.webmanifest`, `icon.svg`).

   Desde la terminal:

   ```bash
   git init
   git add .
   git commit -m "Reto Deming UIDE"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/reto-deming-uide.git
   git push -u origin main
   ```

3. En el repositorio ve a **Settings → Pages**.
4. En *Source* elige **Deploy from a branch**, rama `main`, carpeta `/ (root)` y guarda.
5. Espera 1–2 minutos. Tu app quedará en:

   ```
   https://TU_USUARIO.github.io/reto-deming-uide/
   ```

Cada vez que hagas `git push`, la página se actualiza sola.

---

## Correrla en pantalla completa

### Opción A — Instalarla como app (recomendado para tablet Android)

1. Abre la URL de GitHub Pages en Chrome.
2. Menú (⋮) → **Instalar aplicación** o **Añadir a pantalla de inicio**.
3. Ábrela desde el ícono: arranca en pantalla completa, sin barra de direcciones.

En iPad: Safari → Compartir → **Añadir a pantalla de inicio**.

### Opción B — Modo kiosco en Windows / Mac / Linux

```bash
# Windows
chrome.exe --kiosk --disable-pinch --overscroll-history-navigation=0 https://TU_USUARIO.github.io/reto-deming-uide/

# macOS
open -a "Google Chrome" --args --kiosk https://TU_USUARIO.github.io/reto-deming-uide/

# Linux
google-chrome --kiosk https://TU_USUARIO.github.io/reto-deming-uide/
```

Para salir del modo kiosco: `Alt + F4` (Windows) o `Cmd + Q` (Mac).

### Opción C — Sin instalar nada

Abre la URL en cualquier navegador y toca la pantalla inicial: la app entra en pantalla completa automáticamente, o pulsa `F11`.

---

## Identidad institucional

La aplicación usa el logotipo oficial de la UIDE (tomado de uide.edu.ec) y su paleta corporativa:

| Color | Código | Uso |
|---|---|---|
| Vino tinto UIDE | `#910047` | Color estructural, fondos y degradados |
| Oro UIDE | `#EAAA01` | Acento principal: botones, títulos, datos destacados |
| Oro claro | `#FFD166` | Acento secundario |

El logotipo se muestra sobre una placa blanca, tal como exige el uso correcto de marca sobre fondos oscuros. Los colores funcionales (verde para mejora, rojo para alerta) se mantienen aparte para no confundir la lectura de los datos.

---

## Pantallas compatibles

La app se adapta automáticamente a cada tamaño:

| Dispositivo | Comportamiento |
|---|---|
| Celular vertical | Una sola columna, los 4 indicadores en una fila propia, desplazamiento con la señal "Desliza para ver más" |
| Tablet 10" | Diseño de dos columnas, la mayoría de pantallas caben completas |
| Portátil | Se ajusta también con ventanas de poca altura |
| Kiosco 1920×1080 | Todo cabe sin desplazamiento, que es el modo ideal para el evento |
| Pantalla táctil 65"–86" (4K) | Tipografía, botones y gráfico escalan para verse desde lejos |

Cuando el contenido no cabe, la pantalla se desplaza con el dedo y aparece un aviso flotante indicándolo. En el kiosco de 1920×1080 o más nunca hace falta desplazar.

---

## Uso durante el evento

- La app se **reinicia sola** tras 2 minutos sin actividad, lista para el siguiente visitante.
- Botón **?** en la barra superior: vuelve a mostrar las instrucciones.
- Botón de **sonido**: silencia los efectos si el ambiente es muy ruidoso.
- Botón de **reinicio**: vuelve al inicio de inmediato.
- Duración estimada por visitante: 3 minutos.

---

## Personalización rápida

Todo el contenido está en la sección `/* ---------- CONTENIDO ---------- */` dentro de `index.html`:

- `CASES` — los tres casos: textos, cifras, datos del gráfico y opciones con su impacto.
- `ROLES` — los tres roles seleccionables.
- `LESSONS` — las tres lecciones finales de Deming.

Los colores están en las variables CSS `:root` al inicio del archivo (`--uide`, `--cyan`, `--gold`).

Para agregar el QR de la carrera, reemplaza el bloque `.qrbox` de la pantalla final por una imagen:
`<img src="./qr.png" alt="QR carrera" style="width:64px;height:64px;border-radius:10px">`

---

Universidad Internacional del Ecuador · Ingeniería Automotriz
