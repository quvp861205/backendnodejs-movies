Instalar nodejs: https://nodejs.org/es/download/


Considerando las mejores prácticas para el despliegue:
	Remover contraseñas quemadas.
	Encapsular código spaghetti.
	Revisar la estructura del proyecto.
	Configurar los scripts de build.
	Agregar soporte de caché.
	Añadir HTTPS y CORS.
	Revisar otras prácticas de seguridad.
	
---------------------------------------------------
Diferencias entre Node.js y JavaScript
---------------------------------------------------
En JavaScript dellado del cliente tenemos el DOM y el CSSDOM así como el objeto window 
para manipular los elementos de nuestra página además una serie de APIs, aquí unos ejemplos:

	fetch, SessionStorage y LocalStorage, canvas, bluetooth, audio, web authentication

Mientras que en Node.js no tenemos un DOM ni un objeto windows, lo que sí tenemos son una 
serie de módulos que nos permiten interactuar con los recursos de la máquina como el sistema operativo 
y el sistema de archivos, por ejemplo:

	os (informacion del sistema operativo)
	fs (entrada y salida de archivos)
	http (consumir servicios http)
	util (utilidades generales de nodejs)
	debugger (sistema para debuguear)
	stream (manejo de comunicacion en vivo, se lee un archivo segmento por segmento ya que es muy grande)
	events (administrador de eventos)
	
	
---------------------------------------------------
Node.js v12.11.1 estos son los módulos nativos que vienen por default:
---------------------------------------------------
	Assertion Testing
	Async Hooks
	Buffer
	C++ Addons
	C/C++ Addons - N-API
	Child Processes
	Cluster
	Command Line Options
	Console
	Crypto
	Debugger
	Deprecated APIs
	DNS
	Domain
	ECMAScript Modules
	Errors
	Events
	File System
	Globals
	HTTP
	HTTP/2
	HTTPS
	Inspector
	Internationalization
	Modules
	Net
	OS
	Path
	Performance Hooks
	Policies
	Process
	Punycode
	Query Strings
	Readline
	REPL
	Report
	Stream
	String Decoder
	Timers
	TLS/SSL
	Trace Events
	TTY
	UDP/Datagram
	URL
	Utilities
	V8
	VM
	Worker Threads
	Zlib	