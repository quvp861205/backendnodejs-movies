Ejecutar en el cmd:
	node [archivo.js]
*************************************

Readable y Writable streams
Los Readable y Writeable streams tienen los siguientes eventos y funciones respectivamente:

Readable
	Eventos
		data. Se dispara cuando recibe datos.
		end. Se dispara cuando termina de recibir datos.
		error. Se dispara cuando hay un error.
	Funciones
		pipe
		unpipe
		read
		push
Writeable
	Eventos
		drain. Se dispara cuando emite datos.
		finish. Se dispara cuando termina de emitir.
		error. Se dispara cuando hay un error.
	Funciones
		write
		end
		
Recuerda que tienen estos eventos porque los heredan de la clase EventEmitter.


*************************************************

Duplex y Transforms streams
Ambos sirven para simplificar nuestro código:

	Duplex: implementa los métodos write y read a la vez.
	Transform: es similar a Duplex pero con una sintaxis más corta.

