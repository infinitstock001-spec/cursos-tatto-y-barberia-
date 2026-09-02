# 10 Minutos para Empezar a Cobrar

El código está listo. Falta TU información. Acá está todo, en orden de importancia.

## 1. Links de Mercado Pago (5 min) ← ESTO ACTIVA EL COBRO

1. Entrá a [mercadopago.com.ar](https://mercadopago.com.ar)
2. Login → **Cobros** → **Link de pago**
3. Nuevo link:
   - **Nombre:** Barbería Profesional
   - **Precio:** 49900
   - **Cuotas:** Activá "Hasta 6 cuotas sin interés"
   - **Guardar**
4. Copiá el link que te da

5. Volvé a [academia/js/config.js](academia/js/config.js)
6. Buscá `mercadopago.links` y pegá:

```javascript
mercadopago: {
  activo: true,  // ← CAMBIAR A true
  links: {
    barberia: 'PEGA_EL_LINK_ACÁ',  // ← Link 1
    tatuaje: 'PEGA_EL_LINK_ACÁ',   // ← Link 2
    combo: 'PEGA_EL_LINK_ACÁ',     // ← Link 3
    masterclass: 'PEGA_EL_LINK_ACÁ', // ← Link 4 (opcional)
    mentoria: 'PEGA_EL_LINK_ACÁ',  // ← Link 5 (opcional)
  },
},
```

**Resultado:** Cuando alguien toque "Comprar", se va directo a Mercado Pago. Sin WhatsApp de por medio. El acceso se habilita solo cuando se acredita el pago.

---

## 2. Transferencia (2 min) — Opcional

Si además de Mercado Pago querés que ofrezcan transferencia:

```javascript
transferencia: {
  alias: 'tu.alias.aqui',          // ← Tu alias (ej: mariano.barbero)
  cbu: '1234567890123456789012',   // ← Tu CBU (22 números)
  titular: 'Mariano García',         // ← Tu nombre
  banco: 'Banco Francés',            // ← Banco (informativo)
},
```

Mientras alias y CBU estén vacíos, la opción no aparece. Es seguro.

---

## 3. Pixel de Meta (3 min) — Importante para publicidad

Sin esto no podés hacer publicidad en Instagram que funcione.

1. Entrá a [business.facebook.com](https://business.facebook.com)
2. **Eventos** → **Conectar orígenes** → **Web**
3. **Pixel de Meta** → Dale un nombre → **Continuar**
4. Copiá el **ID** (15 números)
5. En `config.js`:

```javascript
metaPixel: '1234567890123456',  // ← Tu ID aquí
```

**Resultado:** Instagram empieza a rastrear quién visita tu página, quién da click en "Comprar", etc. Cuando hagas publicidad, Instagram ya sabe exactamente a quién mostrar el anuncio (personas que visitaron tu landing).

---

## 4. Google Analytics (2 min) — Opcional pero útil

Podés ver en tiempo real cuánta gente visita, de dónde vienen, qué hacen.

1. [analytics.google.com](https://analytics.google.com) → Nueva propiedad
2. Nombre: "Infinit Academy" → Siguiente
3. Copiá el **ID** (empieza con G-)
4. En `config.js`:

```javascript
googleAnalytics: 'G-1234567890',  // ← Tu ID aquí
```

---

## 5. Cambiar la clave del panel (1 min)

El panel de carga está en `/admin/`. La clave por defecto es `infinit2026`.

```javascript
clavePanel: 'tu_clave_nueva_aqui',  // ← Algo único
```

---

## 6. Verificar tus datos de contacto (30 seg)

Estas líneas son lo que sale cuando alguien compra:

```javascript
whatsapp: '5492613372398',              // ← Tu WhatsApp
email: 'infinitstock001@gmail.com',     // ← Tu email
instagram: 'infinit.academy',           // ← Tu usuario
```

Verificá que sean correctas.

---

## Paso final: Guardar, commit y push

1. Guardás el archivo `config.js`
2. En la terminal:

```bash
cd /home/user/cursos-tatto-y-barberia-
git add academia/js/config.js
git commit -m "Configuración: datos reales de cobro y contacto"
git push
```

3. Cuando Netlify esté conectado y deploy, los cambios salen automático en vivo.

---

## ¿Qué pasa ahora?

- **Mercado Pago activo:** El que compra paga directo, sin WhatsApp.
- **Cupones automáticos:** `/combo?cupon=INSTA10` descuenta 10% en el combo.
- **Leads capturados:** Formularios de "clase gratis" llegan a tu WhatsApp + mail.
- **Medición:** Ves quién vio precios, quién tocó comprar, quién compró de verdad.
- **Modo preventa:** Avisa qué reciben hoy y cuándo llega el resto.

---

## Próximos pasos (cuando Netlify esté live)

1. **Conectar Netlify** (si aún no lo hiciste)
2. **Grabar 3 clases** (las que más importan)
3. **Cambiar testimonios demo por reales** (en `academia/js/data.js`, `testimoniosDemo: false`)
4. **Publicar en Instagram** con los links `/barberia`, `/tatuaje`, `/combo`, `/gratis`

---

**Nota:** El archivo `EMPEZAR-HOY.md` en `academia/` tiene más detalles. Este es el resumen rápido.
