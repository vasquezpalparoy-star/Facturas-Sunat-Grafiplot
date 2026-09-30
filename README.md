# Facturas Sunat Grafiplot

Aplicación web de Grafiplot Vasquez para extraer datos de los PDF de SUNAT y descargarlos con el diseño corporativo. También permite preparar proformas y borradores de boleta.

**Aplicación publicada:** https://grafiplot-documentos.vasquezpalparoy.chatgpt.site

## Uso

1. Selecciona o arrastra un PDF descargado de SUNAT.
2. Revisa cliente, emisor, ítems e importes extraídos.
3. Descarga el PDF con el diseño Grafiplot. Se incluyen las páginas originales como anexo.

Para una proforma, pulsa **Nueva proforma**, completa los datos e ítems y pulsa **Calcular proforma**. Los impuestos, descuentos e importe en letras se ingresan manualmente. Los totales de comprobantes importados no se recalculan automáticamente.

Los archivos se procesan en el navegador. No se envían a un servidor ni se guardan en una base de datos.

## Ejecutar en tu computadora

Necesitas Python 3 o cualquier servidor de archivos estáticos. Desde esta carpeta:

```sh
python -m http.server 8000
```

Abre http://localhost:8000. Usa un servidor HTTP; abrir `index.html` directamente como archivo puede impedir la carga de módulos.

## Alcance

- La extracción está adaptada al PDF con texto del sistema SUNAT SEE SOL y se verificó con una factura E001. Otras estructuras pueden necesitar correcciones manuales.
- Los PDF escaneados no tienen extracción OCR.
- No se emite, firma ni valida un comprobante ante SUNAT.
- Un borrador de boleta no constituye una emisión electrónica.
- El código QR se incorpora desde una imagen proporcionada por el usuario; no se genera una verificación tributaria nueva.
- El logo y los datos del emisor están configurados para Grafiplot. Se pueden cambiar en `logo.png` y `parser.mjs`.

## Archivos

- `index.html` y `style.css`: interfaz.
- `app.mjs`: formulario y creación de PDF.
- `parser.mjs`: extracción de datos.
- `pdf.mjs` y `pdf.worker.mjs`: PDF.js (Apache 2.0).
- `pdf-lib.min.js`: pdf-lib (MIT).

Las licencias de las dependencias se incluyen en sus archivos correspondientes. No se incluyen facturas de clientes ni credenciales en este repositorio.
