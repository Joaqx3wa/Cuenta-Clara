# Cuenta Clara

**Finanzas personales** con una estética cozy en coral, crema, salvia, amarillo mantequilla y lavanda. Aplicación estática compatible con GitHub Pages, sin servidor de datos, cuentas ni servicios externos en tiempo de uso.

## Usar la aplicación

1. Elige **Preparar mi espacio** y completa nombre, moneda, fecha de inicio y saldo de tu cuenta diaria.
2. En **Ajustes**, completa los saldos de Efectivo y Ahorros a esa misma fecha.
3. Usa **Agregar movimiento** para registrar ingresos, gastos, transferencias y aportes o retiros de metas.
4. Selecciona el mes que quieres revisar. Define el presupuesto en su sección y crea tus metas.
5. Agenda pagos. **Registrar pago** crea su gasto automáticamente; no lo registres otra vez.
6. En **Ajustes**, exporta una copia JSON con regularidad. Puedes importarla en otro navegador o dispositivo.

**Ejemplo** permite explorar datos ficticios sin modificar el espacio personal. Cada navegador y perfil tiene sus propios datos. Usar el mismo perfil del mismo navegador comparte el registro. No hay sincronización automática entre dispositivos. Borrar los datos del sitio o usar modo privado puede eliminar el registro local.

## Qué se calcula

- Libre del mes = ingresos − gastos − aportes netos a metas.
- Las transferencias y los aportes a metas mueven dinero entre cuentas; no se cuentan como gastos.
- Los saldos incluyen los importes iniciales y los movimientos hasta el cierre del mes seleccionado.
- El ahorro inicial de una meta forma parte del saldo inicial de Ahorros; no se suma al dinero total.
- Los importes se guardan en céntimos enteros para evitar errores de sumas con decimales.
- Un presupuesto vacío queda sin definir. Cero indica que no se prevé gastar en esa categoría.
- Los pagos mensuales de día 29, 30 o 31 usan el último día del mes si corresponde.
- No se conecta con bancos ni calcula amortizaciones o saldos de tarjetas. Registra pagos de tarjeta como gastos al pagarlos y evita duplicar el mismo importe.

## Copias de seguridad

Exportación e importación con versión de formato y validación de datos. **Unir** agrega identificadores nuevos y conserva los registros, saldos y ajustes existentes. **Reemplazar** restaura la copia completa y requiere confirmación explícita. Las copias contienen información financiera: consérvalas en un lugar privado y no las subas al repositorio.

## Ejecutar localmente

Requiere Node.js 20 o posterior; no se instalan dependencias.

```sh
npm start
npm test
```

Abre `http://127.0.0.1:4173`. El almacenamiento de esta dirección es independiente del de GitHub Pages.

## Publicar en GitHub Pages

El sitio se sirve directamente desde la raíz del repositorio, con rutas relativas compatibles con `/Cuenta-Clara/`.

En **Settings → Pages → Build and deployment**, selecciona **Deploy from a branch**, rama **main**, carpeta **/ (root)** y guarda. La dirección esperada es `https://joaqx3wa.github.io/Cuenta-Clara/` una vez que GitHub termine de publicar.

## Estructura

- `index.html`: entrada de la aplicación.
- `assets/app.mjs`: vistas, formularios y almacenamiento local.
- `assets/model.mjs`: cálculos y validación de copias.
- `assets/style.css`: diseño responsive y accesible.
- `assets/logo.svg`: logo vectorial simple, con la C y una marca de claridad.
- `tests/model.test.mjs`: pruebas de cálculos, cortes de fechas, pagos e importación.

Las tipografías Fraunces y Nunito Sans se distribuyen localmente bajo SIL Open Font License; sus licencias se incluyen en `assets/`. No se cargan analíticas, publicidad, bibliotecas o fuentes de terceros al usar el sitio.
