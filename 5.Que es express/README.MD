¿Que es Express.js?
Express es un framework o marco de trabajo desarrollado sobre Nodejs, lo que quiere decir que provee toda 
la funcionalidad que necesitas para hacer aplicaciones web, permitiendo estructurar tu proyecto de una manera más fácil.
Express.js es un Framework, del creador T.J. Holowaychuk, , inspirado en el framework Sinatra de Ruby. 
Es considerado un framework minimalista, es decir que viene con funcionalidades muy básicas, que luego a medida 
que crezca la aplicación se puede ir extendiendo a través de los módulos que puedes encontrar en npm, 
Además que es el framework de Node.js Más popular.

Template: Como su nombre en espanol lo dice, es una plantilla que podemos usar para apartir de ahi desarrollar nuestro proyecto.

Routing: Es el sistema de rutas que maneja express.js para manejar las rutas de una manera mas facil y sencilla, 
asi podremos ejecutar o mostrar un codigo en determinada ruta o proceso.

Middlewares: Las funciones de middleware son funciones que tienen acceso al objeto de solicitud (req), 
al objeto de respuesta (res), esto quiere decir que es auqella funcion que esta en medio del req y el res, 
y con la cual podemos manipular los datos antes de que lleguen a su destino.

**************************************************************
CONFIGURACION E INSTALACION DEL PROYECTO
	Las librerias se guardaran en node_modules
**************************************************************

Inicializar archivo de configuracion de proyectos:
	npm init -y 

Modificar scripts iniciales:
"scripts": {
    "start": "DEBUG=app:* nodemon index.js", 
    "build": "NODE_ENV=production node index.js"
  }

Configuración de .eslint.json 
Crea el archivo con las siguientes configuraciones

  {
    "parserOptions": {
      "ecmaVersion": 2018                             /** indica la versión de EcmaScript que se va a usar
    }, 
    "extends": ["eslint:recommended", "prettier"],    /** Indica que extienda la versión recomendada y que utilice prettier
    "env": {                                          /** Configura las variables de entorno indicando que se usarán es6, node, mocha
      "es6": true,
      "node": true,
      "mocha": true
    },
    "rules": {                                        /** regla de no poner la consola es unicamente un warning, no un error
      "no-console": "warn"
    }
  }

Se configura prettier
Crear archivo .prettierrc.json

{
  "tabWidth": 2,        /** numero de espacios en los taps 
  "semi": true,         /** que se utilice ; 
  "singleQuote": true   /** comillas simples no dobles
}


instalar express y dotenv  /** prodccion
npm i express dotenv


instalar dependencias de desarrollo:

/* -D abreviatura de --save-dev
npm i -D nodemon eslint eslint-config-prettier eslint-plugin-prettier prettier

/* installar hook para que cuando se haga commit se formatee con eslint y prettier
npx mrm lint-staged

/* Se crea archivo config/index.js de configuracion de variables de entorno ENV 

require('dotenv').config();

const config = {
  dev: process.env.NODE_ENV !== 'procdution',   /** cuando no esté en prodccion */
  port: process.env.PORT || 3000                /** buena practica tener una variable global para el puerto */
}

module.exports = { config };

*************************************
PROBARLO
************************************

npm run dev