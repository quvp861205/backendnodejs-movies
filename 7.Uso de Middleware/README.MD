Ejecutar proyectos:
	npm run dev
	
*****************************************	
	
Middleware
Un Middleware es una capa intermedia que intercepta la información de algo, 
un middleware se define por defecto con una función del siguiente formato:

function (req,res,next){
	next()
}
Donde:
req es un httpRequest() con la información de la petición
res es un httpResponse() con la respuesta de la petición
next es un callback de la siguiente función a llamar

Para definir un middleware que reciba un error, sólo se le agregaría un argumento con el error

function errorHandler(err, req, res, next){
	if(err){
		res.status(err.status || 500);
		res.json({error:err})
	}
	next();
}

*****************************************

Para provocar un error en alguna ruta: throw new Error("BROKEN");

****************************************


¿Qué es Joi y Boom?
Joi(Object Schema Validation). Sirve para validar que los datos que recibimos vengan en el formato adecuado.

Boom(HTTP-friendly error objects). Nos ayuda a imprimir errores comunes en peticiones HTTP de forma sencilla.

instalar Boom: npm i @hapi/boom
Boom
	Boom nos provee una serie de utilidades para retornar errores HTTP, cada utilidad es un objeto de respuesta de tipo Boom que incluye las siguientes propiedades:

	isBoom - si es true indica que es una instancia de Boom.

	isServer - si es true indica que el código de respuesta es mayor o igual 500, aquí más informacion de los codigos de respuesta HTTP status Code.

	message - el mensaje del error.
	typeof - el constructor usado para crear el error (ejemplo: Boom.badRequest).
	output - la respuesta formateada (generalmente esta es la que usamos) y contiene las siguientes claves:

	statusCode - código de estatus HTTP.
	headers - un objeto que contiene encabezados HTTP donde cada clave es un nombre de encabezado y el valor es el contenido del encabezado.
	payload - el objeto formateado usado como respuesta y contiene las siguientes claves:
	- statusCode - código de estatus HTTP, proviene de statusCode
	- error - nombre derivado del error HTTP statusCode.
	- message - mensaje de error derivado de error.message
	

Instalar JOI para validacion de datos: 
	npm i @hapi/joi (version anterior)
	npm i joi (version mas reciente, se requiere reemplazar require('@hapi/joi') por require('joi'))

	Documentacion: https://joi.dev/api/?v=17.4.0
	
	Definir en el directorio utils/schemas las distintas validaciones.
	

************************************************************

A continuación te compartiré una lista de los middlewares más populares en Express.

Body parser
	Analiza los cuerpos de las solicitudes entrantes en un middleware antes que 
	los manejadores de ruta disponibles bajo la propiedad req.body. 
	http://expressjs.com/en/resources/middleware/body-parser.html

CORS
	Middleware para habilitar CORS (Cross-origin resource sharing) en nuestras rutas o aplicación.
	http://expressjs.com/en/resources/middleware/cors.html

Morgan
	Un logger de solicitudes HTTP para Node.js. http://expressjs.com/en/resources/middleware/morgan.html

Helmet
	Helmet nos ayuda a proteger nuestras aplicaciones Express configurando varios 
	encabezados HTTP. ¡No es a prueba de balas de plata, pero puede ayudar! 
	https://github.com/helmetjs/helmet

Express Debug
	Nos permite hacer debugging de nuestras aplicaciones en Express mediante el uso de un 
	toolbar en la pagina cuando las estamos desarrollando. https://github.com/devoidfury/express-debug

Express Slash
	Este middleware nos permite evitar preocuparnos por escribir las rutas con o sin slash al final de ellas. 
	https://github.com/ericf/express-slash

Passport
	Passport es un middleware que nos permite establecer diferentes estrategias de autenticación a 
	nuestras aplicaciones. https://github.com/jaredhanson/passport
	
	