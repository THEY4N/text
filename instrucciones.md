# INSTRUCIONES
# ERRORES DE COSTEO
1. Correr Query en SQLDeveloper ["ERRORES DE COSTEO"](errores_costeo.sql)
2. Mirar si hay o no errores.
3. Mandar evidencia a el grupo de soporte por correo.
---
# CARGUE DE CLINICA
## CARGUE CLINICA VERSALLES

- ir EBS INV ADMNISTRADOR INTERFACE
- abrir la app EBS JAVA
- entrar a ver->solicitudes
- ejecutar nueva solicitud
- aceptar
- poner "xxosi_pro" + (tab)
- principal ventar por planos
- en parametros buscar "clinica versalles"
- ejecutar
- dar click en boton refrescar datos (varias veces)
### ABRIR TEXTO PLANO
- abrir el archivo plano que ellos envian en excel
concatenar "'"....
- copiarlos y pegarlos en la consulta CARGUECLINICAS (debe aparecer vacia)
### ABRIR EBS JAVA
- ir a OM_soporte
- informe solicitudes
- ejecutar solicitud
- (para buscar con CTRL + L)
- buscar solicitud imp... pedidos
- escribir ar (+ tab para que escriba archivos planos)
- en el campo de validad flexfield .. seleccionar "NO"
- aceptar
- ejecutar
- NO
### en el menu de ventanas de la EBS (para cambiar se debe crear nueva solicitud y escoger la clinica)
- selecionar ver(x) -> solicitudes
- boton encontrar
- refrescar
- y realizar de nuevo la consulta CARGUECLINICAS - (aparece llena)
### CORREO
- enviar correo a la clinica para que verifiquen alla.
- **PARA:** 
> Auxiliar Administrativo Versalles <auxadm.versalles@cruzverde.com.co>; juan jimenez <juan.jimenezt@cruzverde.com.co>; RODRIGO YALI <rodrigo.yali@cruzverde.com.co>; Administrador Cruz Verde Farmacia San Marcos <farmacia.sanmarcos@cruzverde.com.co>; Edinson Caicedo <edinson.caicedo@cruzverde.com.co>
- **CC:** 
> Hover Alejandro Ramirez Guzman <alejandro.ramirez@cruzverde.com.co>; Beatriz Elena Bonett Bohorquez <beatriz.bonett@cruzverde.com.co>; Claudia Mileidy Botia Labrador <claudia.botia@cruzverde.com.co>; Jairo Humberto Torres <jairo.torres@cruzverde.com.co> 
----------------------
## CARGUE PORTO AZUL

- ir a la carperta .23
- Carpeta porto azul -> logs (organizar de mas reciente)
- seleccionar el ultimo archivo creado
- copiar el contednido
- abrir excel


## CORRER CONCURRENTE DE ACUERDO A LA CLINICA
### EBS ADMIN_INTERFACE
- ir a Admin_Interface
- ver(x) -> Solicitudes 
- selecionar la opcion **"Ejecutar nueva soliticud"**
- escribir **"xxosi_pro"** + (tab) "debe aparecer programa principal venta por archivos planos"
- seleccionar la clinica que se desea correr
- dar click en el boton **"Ejecutar"**
- dar click en refrescar (varias veces)
#### PARA VER LAS SOLICITUDES SI SE CERRO LA PESTAÑA
- ir a Admin_Interface
- ver(x) -> Solicitudes 
- selecionar la opcion **"Encontrar"**
- dar click en refrescar (varias veces)
---
# INICIADOS *(despues de cargue versalles)*

- admin workflow
- admin workflow
-  work items
- view (errored work item)
- Go
- Factura AP
- APINV_FEA ....
- Retry All -> ok -> ok
- Errored work item y realizar la misma operacion
- Abrir Oracle Aplications
- visualizar resumen facturas
- poner fecha primero del mes y la fecha de hoy
- poner en el campo de estado de el lado izquierdo selecionar iniciado
- dar click en boton encontrar
- click en archivo --> exportar
- ir a la EBS WEB para abrir el excel
- atender solo los que tienen punto (realizar el Query de iniciados)
- realizar un caso Fix
- acciones -> crear un cambio
- poner el texto .
> Buenos días Andres,

> por favor solicitar Ejecución

> FixStandardEBS_1_11092020

> - RECUPERA LINEAS INCIDENTES INV
> - ELIMINA REGISTROS TABLA TEMP ARCHIVOS PLANOS
> -ACTUALIZAR PEDIDOS A NO REQUERIDO

> Anexo Script, formato RFC y evidencia ejecución.

- cambiar la fecha
- poner en categoria Aplicacion EBS
- selecionar opcion crear cambio
- medio
- medio
- **dejar en blanco**
- emergencia
- ENVIAR CODIGO A JAIRO Y ADRIAN
---
# PARADAS DE VIAJES Y PEDIDOS ESTADO ENVIADO
## PARADAS DE VIAJE

-  OM_soporte
-  solicitud interfaces de Envio
-  aceptar
-  ejecutar (solicitudes envio)
-  solicitud unica
-  escribir "inter" en nombre y (presionar tab)
-  interface parada de viaje
-  presionar teclas ctrl + L en parada de viajes
-  entrega
-  de nuevo presion ctrl + L
-  nivel de depuracion -> 1
- aceptar -> ejecutar
- dar click boton SI
- TOMAR PANTALLAZO
- Adjuntar correo grupo soporte

> 65472487-104_FAR_CO_CPREP_BOG:11001-01\09\2020
> el codigo significa numero de viaje - 104 es la  sucursal - y la fecha
entregar el #

## PEDIDO ESTADO ENVIADO
-  modulo OM_SOPORTE
-  (PANTALLA TRANSACCIONES DE ENVIO) ENVIOS -> transacciones
-  poner en "estado Linea" la opcion Enviado
-  fecha de recolecicon poner el primero del mes y un dia antes de la fecha actual
boton encontrar
-  y dar en el boton de enviar
-  Tomar pantallazo y enviar a el grupo de soporte
---
# CASOS DE MESA DE AYUDA

## ERROR UNIDAD

- abrir archivos adjuntos
- copiar el numero de ORDER ENTRY
- copiar el texto largo de referencia
> (**EJEMPLO:** 995226-10092020-25)
- Verficar si existen distintas referencias
- en la EBS buscar en admin_INTERFACE articulos maestra -> principales de articulos
o en OM_maestros artiuculos(si aparece)
- dar F11 -> pegar el numero de pedido(ORDER ENTRY)
- dar CTRL + F11
- verificar la asignacion de la unidad en la sucursal
- corregir en el modulo AR_Correccion_a_terceros -> Receivables -> transacciones -> Receivables : Controlar : Factura Automática
- seleciconar la opcion lineas de interface
- agregar los campos:
> - Id solicitud
> - id linea referencia
> - atributo linea interface 15
> - UDM codigo

- poner check en errores

- borrar el contenido de Id linea interface, id algo, y atributo interface 15
- poner en id solicitud -1

- cambiar la unidad
- grabar

----
## ERROR FACTURACION
### MESA T Y SQL 
- mirar el adjunto abrirlo en excel hay una columna de remision que empieza por 815.. y otra es el numero del pedido 
- se ejecuntan los queries:
> - ["Consulta Pendientes AR ERROR"](Consulta_Pendientes_AR_ERROR.sql)
> - ["Consulta Pendientes AR sin ERROR"](Consulta_Pendientes_AR_sin_ERROR.sql)  (HAY QUE QUITARLE LA FECHA)
> - ["Facturas-pedidos"](Facturas-Pedidos.sql)
> - ["Consulta de emision facturas"](notas.txt)

- solicitar un Fix para cambiar los valores (EDITAR FECHA CONTABLE).
### EBS OM_SOPORTE
- entrar a OM_soporte
- seleccionar organizador de pedido
- pegar el numero del pedido
- boton encontrar
- abrir
- ir a la pestaña de "otros"
- el **deposito** es el numero de la **sucursal** copiar y pegar en un bloc
- en la pestaña superior de "articulos Linea" revisar el articulo del pedido que corresponda a los errores
- se cierra la pestana
- ir a principal de articulos
- se póne el numero de la sucursal
- dar click en el boton buscar
- acceder a la correspondiente
- DAR F11 en el campo organizacion
- pegar el numero del articulo
- y CTRL + F11
- en el lado izquierdo hay 4 pestañas hacer click en la que dice **asignaicon de organizacion**
- dar click en el boton atributos ORG
### EBS ADMIN_INTERFACE
- IR Al modulo admin_interface
- en articulos maestra 
- dar opcion principales de articulos
- se póne el numero de la sucursal
- dar click en el boton buscar y acceder a la correspondiente
- DAR F11 en el campo organizacion
- pegar el numero del articulo
- y CTRL + F11
- en el lado izquierdo hay 4 pestañas hacer click en la que dice **asignacion de organizacion**
- verificar que esten inactivos en las sucursales F00, OSI y la del problema
- se el escala a JAVIER CRUZ o ANDRES CABRERA


PARA VERIFICAR
## Estado cerrado
### EBS OM_SOPORTE
ir a OM_soporte
organizadorde pedido
ingresar numero de pedido
dar click en el boton de acciones

300-336826 : Incidente NO GENERAN FACTURAS



305876514
305876514
305876514
306343259
306346951
306346951
306346951
306346951
306348316
306351990
306831342
306833471
306833471
306853332
306853332


# TAREAS DE LA MAÑANA
- [ ] Errores de costeo
- [ ] Cargue de Clinica Versalles
- [ ] Cargue de Clinica Porto Azul
- [ ] Iniciados
- [ ] Paradas de Viajes
- [ ] Pedidos estado enviado
### CASOS
- > Codigo Caso: <input type="text" id="name" name="name"/>
- > Codigo Caso: <input type="text" id="name" name="name"/>
- > Codigo Caso: <input type="text" id="name" name="name"/>
- > Codigo Caso: <input type="text" id="name" name="name"/>
- > Codigo Caso: <input type="text" id="name" name="name"/>
- > Codigo Caso: <input type="text" id="name" name="name"/>
- > Codigo Caso: <input type="text" id="name" name="name"/>
- > Codigo Caso: <input type="text" id="name" name="name"/>
