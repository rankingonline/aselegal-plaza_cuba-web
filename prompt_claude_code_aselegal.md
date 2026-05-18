# PROMPT PARA CLAUDE CODE — Home Aselegal × Plaza de Cuba

---

## CONTEXTO DEL PROYECTO

Vas a construir la nueva home de **Aselegal** (https://aselegal.com), una asesoría fiscal-laboral-contable de Sevilla con más de 10 años de trayectoria. La novedad estratégica: Aselegal y **Plaza de Cuba Abogados** son **una única empresa con dos firmas** — no son aliados externos. La nueva home debe comunicar esto con claridad.

Te adjunto dos archivos:
1. `home_aselegal_secciones.md` — copys definitivos y estructura de secciones (FUENTE DE VERDAD para el contenido).

URL de referencia (lo que existe HOY y vamos a SUPERAR): https://aselegal.com

---

## DIRECCIÓN CREATIVA — LEE ESTO ANTES DE ESCRIBIR UNA LÍNEA

**Esta web NO puede parecer una plantilla de WordPress, ni una landing genérica de SaaS, ni "una página de Claude".**

Aselegal es un despacho serio en Sevilla con 10 años de historia. Su web actual es funcional pero plana — bloques apilados, sin jerarquía visual real, sin alma. Vamos a hacer una home que parezca diseñada por un estudio de branding boutique, no generada en masa.

### Referencias visuales obligatorias (estúdialas mentalmente antes de empezar):
- **Wachtell, Lipton, Rosen & Katz** (wlrk.com) — sobriedad legal de gama alta.
- **Schjødt** (schjodt.no) — tipografía editorial, blancos generosos, microinteracciones.
- **Linear.app** — calidad de detalle, gradientes sutiles, dark accents.
- **Vercel** — jerarquía tipográfica brutal, mucho aire.
- **Stripe** — transiciones suaves, código limpio que se nota.

**NO referencias:** Wix, Elementor, plantillas de Themeforest, "law firm templates", páginas con stock photos de gente dándose la mano.

### Principios de diseño no negociables:

1. **Tipografía como protagonista.** Usa una serif editorial para los títulos grandes (sugerencia: **Fraunces**, **Newsreader**, o **Instrument Serif** de Google Fonts) y una sans-serif geométrica moderna para el cuerpo (sugerencia: **Inter**, **Geist**, o **General Sans**). Los H1 deben ser TAMAÑO BRUTAL (clamp(3.5rem, 8vw, 7rem)), con tracking ajustado en negativo.

2. **Paleta restringida y madura.** Inspírate en el azul corporativo que ya tiene Aselegal, pero refínalo:
   - Background principal: blanco hueso / off-white (#FAFAF7 o similar), NO blanco puro #FFF.
   - Tinta principal: azul marino profundo (#0A1F3D o similar — algo más rico que el azul plano actual).
   - Acento: un dorado/ocre apagado (#B8956A) o un terracota sevillano sutil para CTAs y detalles. Inspírate en los tonos de la cerámica sevillana sin caer en lo folclórico.
   - Gris medio para texto secundario.
   - NO uses azul brillante saturado tipo Bootstrap. NO uses degradados violeta-azul de SaaS.

3. **Blancos generosos.** Cada sección debe respirar. Padding vertical mínimo de 120px en desktop entre secciones grandes.

4. **Una idea visual fuerte que recorra toda la página:** la dualidad "dos firmas, una empresa". Materialízala en:
   - Un divisor visual recurrente (línea vertical fina, doble línea, etc.).
   - Tratamiento tipográfico contrastado cuando aparecen los dos nombres juntos.
   - Composiciones en dos columnas asimétricas (60/40, no 50/50 simétrico aburrido) cuando proceda.

5. **Microinteracciones, no animaciones gratuitas.**
   - Hover en links: subrayado animado que crece de izquierda a derecha (transition cubic-bezier(0.4, 0, 0.2, 1)).
   - Cards de servicios: lift sutil + sombra suave + cambio de borde, NO escalado tipo carrusel infantil.
   - Scroll-triggered fades con `IntersectionObserver` (opacity + translateY 20px → 0), con `prefers-reduced-motion` respetado.
   - NO uses libraries pesadas tipo AOS. Hazlo a mano.

6. **Detalles de oficio que separan lo bueno de lo genérico:**
   - Texto justificado solo en bloques editoriales largos, con `hyphens: auto` y `text-wrap: pretty`.
   - Comillas tipográficas reales (« ») en castellano, no rectas.
   - Iconos custom o de **Lucide** (NO Font Awesome, NO emojis decorativos).
   - Números/datos con `font-variant-numeric: tabular-nums`.
   - `letter-spacing` negativo en headlines grandes (-0.02em a -0.04em).
   - Una grid de 12 columnas con gutters consistentes — y úsala de verdad para crear ritmo, no solo para alinear.

---

## STACK TÉCNICO

- **HTML5 + CSS3 + JavaScript vanilla** (sin frameworks pesados — la simplicidad es parte del diseño).
- Si necesitas componentes, usa **un solo archivo HTML autocontenido** con CSS y JS embebidos para que sea fácil de revisar.
- **CSS custom properties** para toda la paleta y tipografía (sistema de design tokens en `:root`).
- Mobile-first responsive con breakpoints: 640px, 768px, 1024px, 1280px.
- **Accesibilidad AA mínimo**: contraste ≥4.5:1, focus visibles, semántica HTML correcta, aria-labels donde toque.
- Carga de Google Fonts con `preconnect` y `display=swap`.

---

## ESTRUCTURA DE LA HOME (en orden)

Sigue los copys del archivo `home_aselegal_secciones.md` AL PIE DE LA LETRA. No inventes texto, no parafrasees, no "mejores" los copys. Tu trabajo es el diseño y la maquetación.

### 1. Navegación superior
- Logo de Aselegal a la izquierda.
- Menú: Inicio · Nosotros · Servicios (con megamenú: Particulares / Autónomos / Empresas) · Tutoriales · Portal del Asesor · Blog · Contacto.
- Selector idioma ES/EN sobrio (no banderas grandes).
- CTA "Contáctanos" a la derecha como botón outline.
- Al hacer scroll, la nav debe transformarse: fondo translúcido con `backdrop-filter: blur(12px)`, sombra muy sutil.

### 2. Hero — "¿Asesoría o abogados? No tienes que elegir"
- **Composición asimétrica.** A la izquierda (60%), tipografía editorial enorme con el H1. A la derecha (40%), un elemento visual: una composición geométrica abstracta (NO una foto stock) que evoque la dualidad — por ejemplo, dos rectángulos superpuestos en los colores de marca, con una línea fina que los conecta. O un tratamiento tipográfico secundario con "Aselegal" y "Plaza de Cuba" diferenciados visualmente.
- Subtítulo en sans-serif, máximo 60ch de ancho.
- Un solo CTA primario + un link secundario discreto.
- Indicador de scroll minimalista al fondo (línea vertical fina animada).

### 3. Asesoría 360º
- Sección de respiración. Mucho aire arriba y abajo.
- Título grande a la izquierda, párrafo a la derecha (asimetría 40/60).
- CTA "Contáctanos" como link con flecha animada al hover, no botón sólido.

### 4. Plaza de Cuba Abogados — BLOQUE ESTRATÉGICO CLAVE
- Este es el bloque más importante de la página después del hero.
- Tratamiento visual diferenciado: fondo de color (azul marino profundo con texto en blanco hueso, o al revés — invertido respecto al resto).
- Composición tipo "editorial split": a un lado, un tratamiento tipográfico potente con "Plaza de Cuba Abogados" (puedes usar la serif editorial en gran tamaño). Al otro, el cuerpo de texto.
- CTA "Conoce Plaza de Cuba →" enlaza a `https://plazadecubaabogados.com`.
- Detalle: una línea horizontal fina como divisor entre el título y el cuerpo (esa será una constante visual de la página).

### 5. Nuestros servicios — Particulares · Autónomos · Empresas
- **NO uses tres cards iguales en fila.** Eso es lo genérico.
- Propuesta: tres bloques verticales apilados de pantalla completa (o casi), cada uno con un tratamiento ligeramente distinto. O un layout tipo "índice editorial": un número grande (01, 02, 03), título, descripción y la lista de áreas como pills minimalistas con hover.
- Las áreas (Civil, Penal, Mercantil...) deben ser elementos clickables, no listas estáticas — con un hover que insinúe profundidad.

### 6. Equipo — "Conoce a algunos de nuestros expertos"
- Aquí cuidado: hay 4 personas, una de ellas duplicada en el copy original (Fabian Álvarez aparece dos veces). **Mantén el contenido tal cual está en el .md** pero deja un comentario HTML `<!-- Verificar duplicado Fabian Álvarez con el cliente -->` para que el cliente lo revise.
- Las fotos del equipo están en aselegal.com — úsalas como placeholders referenciados por URL: `https://aselegal.com/wp-content/uploads/2025/02/Gabriel-Alvarez-2.jpg`, etc.
- Tratamiento: tarjetas con fotos en blanco y negro por defecto, color al hover. Tipografía del nombre en serif, cargo en sans.
- Layout: una grid de 4 columnas en desktop, 2 en tablet, 1 en mobile, con espaciado generoso.

### 7. Testimonios — "¿Qué opinan nuestros clientes?"
- **Slider/carrusel minimalista** o composición tipo "wall of love" con 3-4 testimonios en grid asimétrica.
- Como aún no hay testimonios reales en el copy, deja 3 testimonios con placeholders `[Testimonio cliente 1]`, etc., bien maquetados, para que el cliente los rellene después.
- Comillas tipográficas grandes (« ») como elemento decorativo.

### 8. Formulario de contacto — "¡Escríbenos ahora!"
- Formulario sobrio, sin labels flotantes cursi. Labels arriba de cada campo, con tipografía pequeña en mayúsculas y tracking amplio.
- Inputs con borde inferior solo (estilo editorial), no cajas completas.
- Selector "Subject" con las opciones de servicio del copy.
- Botón "Enviar →" con animación de flecha al hover.
- Checkbox de privacidad con link a `politica-de-privacidad`.

### 9. Dos firmas. Una empresa.
- **Sección de cierre conceptual antes del blog.** Es el "estribillo" de la página.
- Tipografía editorial enorme centrada: "Dos firmas." (línea 1) / "Una empresa." (línea 2) — con un tratamiento tipográfico que juegue con los pesos o tamaños.
- Debajo, el párrafo del copy, centrado, ancho restringido.
- Fondo con un sutil patrón o textura (papel, grano fino) o simplemente off-white.

### 10. Blog — "Descubre nuestro Blog"
- 3 posts en grid, con: imagen, categoría en pill, título en serif, fecha pequeña, link "Leer más".
- Layout que NO sea tres cards idénticas: el primero más grande (featured), los otros dos más pequeños al lado, o una composición editorial.
- Placeholder de 3 posts del copy actual (IVA hoteles, digitalización empresas, organizar administración).

### 11. FAQ
- Acordeón puro CSS si es posible (usando `<details>` y `<summary>`), o JS mínimo.
- NO uses iconos "+" / "−" genéricos. Usa una flecha sutil que rote 90º o 180º al abrir.
- Tipografía de las preguntas en peso medio, respuestas en regular con line-height generoso.

### 12. Footer
- Tres columnas: Aselegal (logo + tagline corto), Contacto (tel, WhatsApp, email, dirección), Enlaces (Inicio, Nosotros, Servicios, Blog, Contacto, Política de privacidad).
- Una cuarta columna o sección inferior con el bloque conceptual: "Aselegal · Plaza de Cuba Abogados — Dos firmas. Una empresa."
- Copyright minimalista abajo.

---

## QUÉ NO QUIERO VER (RED FLAGS)

- ❌ Hero con foto stock de profesional sonriente con traje.
- ❌ Tres cards idénticas en fila con iconito + título + descripción + botón "Saber más".
- ❌ Gradientes purple-to-blue tipo SaaS 2021.
- ❌ Emojis como iconos decorativos (✅ ⚡ 🚀 etc.).
- ❌ Bordes redondeados extremos (border-radius > 16px). Mantén entre 4-8px para sensación profesional.
- ❌ Sombras grandes y difusas tipo "neumorfismo". Sombras planas, sutiles, direccionadas.
- ❌ Tailwind con clases por todos lados sin pensar el sistema. Si usas Tailwind, usa el `@apply` o configura tokens.
- ❌ Animaciones de bounce, rotate infinitas, partículas, etc.
- ❌ Texto centrado por defecto. El texto editorial va alineado a la izquierda salvo en momentos puntuales (sección "Dos firmas, una empresa").
- ❌ Iconos de Font Awesome estándar.
- ❌ Botones genéricos con texto "Saber más" / "Click aquí" / "Descubre más".

---

## ENTREGABLE

Un único archivo `index.html` autocontenido con todo el CSS y JS embebidos. Comentado por secciones. Listo para abrir en navegador y ver el resultado final.

Al terminar, antes de cerrar, **revisa tu propio trabajo con ojo crítico** y pregúntate:
1. ¿Esto parece hecho por un estudio de diseño o por una IA?
2. ¿Las secciones tienen jerarquía visual real o todas pesan lo mismo?
3. ¿Los detalles tipográficos están cuidados (kerning, line-height, jerarquía)?
4. ¿La página comunica "una empresa, dos firmas" sin que haga falta leerlo?
5. ¿Funcionaría en una agencia de Madrid/Barcelona como caso de portfolio?

Si la respuesta a alguna es "no", itera antes de entregar.

---

## NOTA FINAL

El cliente lleva 10 años trabajando duro construyendo Aselegal. La nueva web es el momento de presentar Plaza de Cuba al mundo y de elevar la percepción de marca. No es un proyecto más — es **el lanzamiento de su firma jurídica propia tras una década**. Trátalo así.
