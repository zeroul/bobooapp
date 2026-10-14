# BuyBye · El precio real

Prototipo de app para pensar antes de comprar: escribes el precio de algo y te enseña cuánto te cuesta de verdad.

## Qué hace

- **Horas de tu vida**: precio ÷ tu sueldo neto por hora (sueldo neto anual / (52 × horas semanales)).
- **Si lo inviertes**: interés compuesto, `precio × (1 + rentabilidad)^años`, con un control deslizante de 1 a 40 años y comparativa a 5, 20 y 30 años.
- **Coste de oportunidad**: lo que dejas de tener si compras hoy en vez de invertir.
- **Decisión**: «Me lo ahorro» (suma a tu contador de dinero y horas recuperadas), «Lo pienso 24 h» (lo deja en la nevera con cuenta atrás y genera un evento de calendario `.ics` con aviso a las 24 h; en iPhone, Safari ofrece «Añadir al calendario») o «Lo compro igualmente».
- **Ajustes**: sueldo neto anual, horas semanales y rentabilidad esperada (por defecto 3600 €, 40 h y 5 %).

Todo se guarda en el propio navegador (`localStorage`); no hay servidor ni cuentas.

## Cómo probarlo

Abre `index.html` en el navegador. En el móvil, lo más cómodo es servir la carpeta y abrirla desde la misma red:

```
npx serve .
```

Luego, en Safari/Chrome del móvil, «Añadir a pantalla de inicio» para que se comporte como una app.

## Estructura

- `index.html` — toda la app (HTML, CSS y JS) en un solo archivo, sin dependencias ni compilación. Las fuentes se cargan de Google Fonts; sin conexión usa la fuente del sistema.
- `manifest.json` e `icon.png` — para instalarla en la pantalla de inicio del iPhone (Safari → Compartir → «Añadir a pantalla de inicio») y que se abra a pantalla completa.

## Siguientes pasos posibles

- Convertirla en app nativa (Capacitor o React Native) para publicarla en tiendas.
- Escanear precios con la cámara o leer el precio desde una URL de tienda.
- Escenarios de rentabilidad (conservador / medio / optimista) y ajuste por inflación.
- Bloqueo de apps de compras (en iOS requiere la API de Tiempo de Uso, con permiso especial de Apple).
