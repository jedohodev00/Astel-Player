# Astel · sitio web (GitHub Pages)

Sitio estático de Astel: portada, privacidad, términos y borrado de datos.
Sin dependencias externas (CSS propio + SVG en línea), sin cookies y sin
analítica.

## Contenido

```
index.html          portada (funciones, dispositivos, cómo funciona, FAQ, soporte)
privacidad.html     política de privacidad
terminos.html       términos de uso
eliminar-datos.html cómo borrar los datos
404.html            página no encontrada
en/                 versión en inglés de las cuatro páginas
assets/estilo.css   estilos compartidos
.nojekyll           evita que GitHub Pages procese el sitio con Jekyll
```

El selector **ES / EN** de la cabecera enlaza cada página con su equivalente:
`privacidad.html` ↔ `en/privacy.html`, `terminos.html` ↔ `en/terms.html`,
`eliminar-datos.html` ↔ `en/delete-data.html`.

## Aviso legal al entrar

La portada (ES y EN) muestra un cuadro de diálogo la primera vez que se visita,
con el aviso de que Astel es solo un reproductor y no aloja ni distribuye
contenido. El propio aviso tiene **selector de idioma**: si eliges English, el
texto cambia a inglés y al continuar te lleva a la versión inglesa del sitio.

Se recuerda en `localStorage` con la clave `astel_aviso_legal_v1`; para volver a
verlo, bórrala desde las herramientas del navegador o pulsa **Aviso legal** en el
pie. Si cambias el texto del aviso, sube el número de la clave (`v2`) para que se
vuelva a mostrar a todo el mundo.

## Publicar en GitHub Pages

1. Sube el contenido de esta carpeta a un repositorio.
2. Settings → Pages → Build and deployment:
   - Source: **Deploy from a branch**
   - Branch: `main` y carpeta `/ (root)` (o `/docs` si lo metes ahí).
3. Espera 1-2 minutos. La URL aparece en la misma pantalla.

Con dominio propio: Settings → Pages → Custom domain, y en el DNS del dominio:

```
CNAME   www   <usuario>.github.io.
A       185.199.108.153
A       185.199.109.153
A       185.199.110.153
A       185.199.111.153
```

GitHub crea solo el fichero `CNAME`; si quieres, añádelo a mano en la raíz.

## ¿Se puede tener el repositorio privado?

Decisión actual: **repositorio público, solo con la web** (estas cuatro páginas y
`assets/`). El código de la app y los instaladores no viven aquí.

Si algún día quieres ocultar el código fuente, hay que separar dos cosas:

- **Repositorio privado**: en cuenta personal requiere **GitHub Pro** (o superior);
  en organización, **GitHub Team**. En el plan Free el repositorio tiene que ser
  público para usar Pages.
- **Sitio privado**: no es posible en planes normales. Aunque el repositorio sea
  privado, **la web publicada es pública** (así lo indica GitHub). Para un sitio
  con acceso restringido haría falta GitHub Enterprise Cloud.

Alternativa sin pagar GitHub: **Cloudflare Pages** (o Netlify/Vercel) con el
repositorio privado. Es gratis, el código no queda expuesto y se puede usar
dominio propio. En ese caso se sube esta misma carpeta.

## Importante: no metas instaladores en el repositorio

Los `.apk`, `.wgt`, `.ipk` y `.exe` **no** deben vivir en este repositorio si es
público (cualquiera podría descargarlos desde el código, no solo desde la web).
Déjalos en el servidor de descargas o en un bucket con enlaces firmados, y que
la web solo enlace a la página de soporte.

## Editar

- Colores y tipografía: variables al principio de `assets/estilo.css`.
- Dispositivos disponibles: sección `#dispositivos` de `index.html`.
- Fecha de las páginas legales: etiqueta `.fecha` de cada página.
