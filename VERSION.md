VERSION 0.4.25
Modificaciones en el SDK para que no permita crear empresas repetidas. Lo mismo para sucursales, puntos de venta y cajas.
Se modificaron los test del Sandbox para que todos muestren un mensaje de error en el caso que existan.
Se creo nuevo test de Register Company con datos válidos para la prueba.

VERSION 0.4.24
Se agregó un control que valida que ambas versiones(SDK y .aar) tengan la misma versión.
En caso de no coincidir arrojará un mensaje para indicar actualizar las mismas.
Ya no se tendrá que agregar manualmente una jurisdicción por defecto desde su aplicación, ya lo hace el SDK. Ver ejemplo en Sandbox, en el metido initFiscalManager().
Nuevos constructores. Se agregaron constructores con menos parámetros para que puedan usar esos en vez de los originales y ponerle parámetros null o false sin utilidad. Se agregó nuevo Test en Sandbox, FP_FACTURA_A, en el cual se utiliza el nuevo constructor.
"Invalida parameter exception" al querer imprimir un cierreZ en impresora 2gen. 
Se agregó validacion en metodo TipoHabilitacion() para valores incorrectos ya que detectamos (debugeando el SDK mientras corríamos la aplicación de Clover) que se llamaba a ese método luego de realizar un Cierre Z. Se probó desde la aplicación de Clover Fiscal Printer y funcionó correctamente. Igualmente esto no soluciona el problema de raíz ya que sospechamos que se debe estar llamando de forma incorrecta a la función debido que en nuestro Sandbox no tenemos ese error.
Por ese motivo pedimos el fragmento del código de la aplicación de Clover para que podamos revisarlo.