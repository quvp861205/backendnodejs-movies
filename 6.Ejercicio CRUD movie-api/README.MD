Ejecutar proyectos:
	npm run dev
	
Generar json aleatorios bajo una estructura definida:
	https://www.mockaroo.com/

Crear una cuenta para utilizar un servicio en la nube de mongodb
	https://www.mongodb.com/cloud/atlas	
	
	Configuracion:
		Network Access: Permitir todas las ips
		Database Access: [permissions: Read and write, user: db_user, pass: 1234]
		Create database: [database: platzivideos_db, collection: movies]
		
	Ambientar proyecto con mongodb:
		instalar mongo: npm i mongodb
		agregar variables de entorno de mongodb en el proyecto (.env)
		agregar las variables entorno al config.js
		crear la libreria mongodb para el proyecto (lib/mongo.js)
		
	Clientes para manejar mongodb:
		https://robomongo.org/download
		https://www.mongodb.com/download-center/compass
		
	Manual de como hacer CRUD con mongo:
		https://docs.mongodb.com/manual/crud/