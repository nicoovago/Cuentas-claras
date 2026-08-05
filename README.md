# Depósitos

Registro de depósitos de Mercado Pago: importás el CSV que exporta tu cuenta y la app te lo ordena por fecha o por nombre, con totales por día y por persona.

Una sola página HTML, sin build, sin servidor, sin backend. Los datos se guardan en el navegador (`localStorage`) y nunca salen del dispositivo.

## Qué hace

- Importa el CSV de Mercado Pago (Actividad o Liberaciones) desde archivo o pegándolo como texto.
- Detecta sola las columnas de fecha, nombre y monto; si tu reporte usa otros encabezados, los elegís a mano antes de importar.
- Ordena por **fecha** (más nuevo / más viejo), **nombre** (A→Z / Z→A) o **monto**, y agrupa según el criterio: por día con el subtotal del día, o por letra inicial.
- Entiende montos en formato argentino (`$ 15.000,50`) y fechas `DD/MM/AAAA` además de ISO.
- Evita duplicados si reimportás el mismo reporte.
- Buscador por nombre o detalle, carga manual, resumen por persona y exportación del listado ya ordenado.
- Por defecto muestra solo entradas de dinero; hay un check para incluir las salidas.

## Cómo usarla

Abrí `index.html` en cualquier navegador. Nada más.

Para publicarla: subí el repo a GitHub, andá a **Settings → Pages**, elegí la rama `main` y la carpeta `/ (root)`. En un minuto queda en `https://TU-USUARIO.github.io/TU-REPO/`.

## De dónde sale el CSV

En Mercado Pago: **Tu negocio → Reportes** (o **Actividad → Descargar**), generá el reporte de **Actividad** o de **Liberaciones de dinero** en formato **CSV**, y ese archivo es el que importás.

## Limitaciones

- **No se conecta a Mercado Pago.** Trabaja con el CSV que exportás vos. Automatizarlo requiere la API de Mercado Pago con un access token, y un token no puede vivir en una página estática: lo vería cualquiera que mire el código. Eso necesita un backend mínimo.
- Los datos viven en el navegador que usaste. Si borrás los datos de navegación, se van. Exportá el CSV si querés respaldo.
- El parseo asume día/mes/año en las fechas con barras y coma decimal en los montos.

## Dependencias

[PapaParse 5.4.1](https://www.papaparse.com/) por CDN, para leer el CSV. Es lo único externo.

## Licencia

MIT.
