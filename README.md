# sales_products
App en php que realiza la gestion de inventario(CRUD) y la venta del mismo

1. pasos para desplegar localmente el aplicativo

descargar y abrir xampp, abrir apache y mysql, importar la base de datos de nombre dbkonecta a my sql "solo seleccionar e impoprtar no se debe hacer nada mas con ella" siguiente debes abrir la ruta "http://TUlocalhost/pages/login/login.html

PDT: La base de datos la en cuentras para importar en la siguiente ruta: proyect_php/control_inventarios/db/bdkonecta.sql

2. para realizar login debes registar un usuario esto lo puesdes hacer desde el interior de la app por lo que te doy acesso con el siguiente usuario USER: admin@admin.com y PASSWORD: admin123 una vez dentro del app debes ir a crear productos para visualizar el producto y realizar las funcionabilidades.

PDTA: tener en cuenta dentro del proyecto el archivo dentro de la carpeta "proyect_php/control_inventarios/php/dto/dto_connection" configurar la conexion a la base de datos de mysql

Consultas de BD:


/* consulta que permita conocer cuál es el producto que más stock tiene.*/

SELECT name,stock FROM `create_product` WHERE stock=(select max(stock) from create_product)

/*consulta que permita conocer cuál es el producto más vendido.*/

SELECT CP.name FROM create_product CP INNER JOIN sell_product SP ON CP.product_id=SP.sell_product_id WHERE SP.sell_product_howmany=(select max(sell_product_howmany) from sell_product)


Quedo atento