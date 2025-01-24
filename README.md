Creación Request de Certificado Digital Windows en la Linea de Comandos

Desde la línea de comandos CMD también es posible hacerlo. Sus principales ventajas
son:

· Portabilidad entre versiones antiguas y recientes de Windows.
· Es interno; no requiere programas adicionales.
· Mucho más rápido y flexible para automatizaciones.

Para minimizar la generacion del request como generalmente se hace desde el MMC, se tiene este archivo Request.inf que puede ser utilizado para generar el archico CSR

A continuación se abre CMD como Administrador y escribimos el comando en su forma general:

certreq -new Request.inf NombreDelRequest.csr

Se pueden especificar sus ruta por separado. Un request, típicamente, lleva el mismo nombre del servidor. Por ejemplo:
certreq -new d:\servidores\inf\miserver.inf d:\servidores\request\miserver.csr

La uniformidad de los archivos, repetición en el tiempo y su frecuencia de renovación permiten optimizaciones como generar N archivos *.inf (uno por cada servidor con su nombre) y mantenerlos en una carpeta dedicada. Los request, a su vez, podrían tener su carpeta y la generación “envolverse” en simples BAT.
