Despliegue en Now (Vercel  https://vercel.com/)

Ahora Now se llama Vercel, así que les dejo los pasos que seguí para hacer mi despliegue:

Instalar vercel globalmente: npm i -g vercel
Añadir las variables de entorno para conectarse a la bd de mongo a la lista de variables secretas de vercel:
	vercel secrets add platzivideos-db-user ...
	vercel secrets add platzivideos-db-password ...
	vercel secrets add platzivideos-db-host ...
	vercel secrets add platzivideos-db-name ...
	
En vez de los ... se deben colocar las variables de entorno respectivas (las mismas del archivo .env).
Talvez necesites crear una cuenta en Vercel ya que te pedirá un email cuando hagas esto.
Para ver las variables secretas guardadas (no se ven los valores): vercel secrets ls

Ahora añadimos un archivo vercel.json en la raíz del proyecto con el siguiente contenido:
	{
	  "name": "platzivideo",
	  "version": 2,
	  "builds": [
		{
		  "src": "index.js",
		  "use": "@vercel/node"
		}
	  ],
	  "routes": [
		{
		  "src": "/(.*)",
		  "dest": "/index.js"
		}
	  ],
	  "env": {
		"DB_USER": "@platzivideos-db-user",
		"DB_PASSWORD": "@platzivideos-db-password",
		"DB_HOST": "@platzivideos-db-host",
		"DB_NAME": "@platzivideos-db-name"
	  }
	}
	
Antes de desplegar podemos probar la app con vercel dev. Una vez ejecutado este comando se nos preguntarán algunas 
cosas que podemos responder por defecto (dando enter y enter). Al final la aplicación quedará desplegada como si 
estuviera en producción pero localmente.

Si todo anda bien, hacemos el despliegue: vercel. 
El proceso tardará unos segundo y cuando finalice se mostrará la URL del proyecto ya desplegado.
Para configurar una URL más amigable: vercel alias <url_actual> <alias>

Para hacer esto es necesario que tengas acceso a la URL alias dentro de tu cuenta.
Aquí esta mi app desplegada https://movies-api-silk.vercel.app/api/movies


******************************
Para probar localmente: vercel dev

Para liberar en los servidores de vercel: vercel 
	(genera una url automaticamente donde se puede consumir la api en internet)
Ejemplo de Cambiar la url de la api a una mas amigable:
	vercel alias https://platzivideo.glrodasz.vercel.sh platzivideo-api.vercel.sh
	