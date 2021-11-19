AVISO -------------------------------------------------------------------
La práctica está incompleta, hace falta revisar algunas fallas respecto a la conexión con el servidor y el servidor de respaldo
ya que durante la conexión si uno de los dos servidores está conectado, falta que los datos se almacenen en una de las dos bases de datos
pero si ambos están conectados, los datos se almacenan en orden distinto y ambos servidores responden a las peticiones de los clientes al
mismo tiempo, tengo en mente la idea de que es por los sockets multicast utilizados, así que es necesario reparar ese bug. 

Básicamente el funcionamiento de la práctica es que ambos servidores almacenen los datos en ambas bases para mantener la consistencia de los
datos, los relojes de los clientes se generan de forma aleatoria, ya que esos eran los requerimientos de la práctica, pero se puede aplicar 
la sincronización de los relojes mediante un algoritmo distribuido como el algoritmo de Cristian. 

Los clientes sólo pueden pedir una vez el libro, no puede haber repeticiones a menos que la sesión del servidor se reinicie, y en caso de que
los libros se terminen, o sea, ya no haya más libros que repartir, el servidor notifica a los clientes que ya no hay libros y les pregunta si
quieren reiniciar una nueva sesión, cuando esto sucede se genera un botón en el cliente que manda la petición de reinicio de sesión y solamente
el servidor podrá decidir cuando se realiza el reinicio de la misma.
