---
layout: post
title: Introducción a Grunt, The Javascript Task Runner
date: 2015-08-26 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img:   grunt.png # Add image post (optional)
tags: [Holidays, Hawaii]
---
Hola a todos, en este tutorial quiero hablaros de una librería javascript esencial en el desarrollo frontend, se trata de Grunt.

Grunt esta catalogada como un “Task Manager”, es decir, su función es automatizar acciones repetitivas de tal manera que ahorremos esfuerzo y tiempo para invertirlo en otras labores de nuestro proyecto.

De entre las tareas que podemos automatizar algunas de ellas son:
<ul>
	


<li>Arrancar el servidor.</li>
<li>Compilar.</li>
<li>Comprimir imágenes.</li>
<li>Lanzar test unitarios</li>
<li>Minimizar fichero css</li>
<li>Minimizar código javascript (uglify)</li>
<li>Concatenar ficheros.</li>
<li>Observar si nuestro código tienes errores (watch), etc, ….</li>
</ul>


##Como instalar Grunt

Para poder usar Grunt primero debemos tener instalado Node, ya que se trata de un “npm” (Node Package Manager) , para instalarlo usaremos

1.  npm install grunt –save­-dev

Esto lo que hace es instalar grunt de forma global, a continuación hay que instalar el cliente

1.  npm install ­g grunt-­cli

Una vez instalado, nos generará un fichero js, llamado “Gruntfile“, en el cual se definirá la configuración de las tareas a automatizar.

##Estructura del fichero Gruntfile

Ahora vamos a abarcar la configuración de Grunt, mediante su fichero, el cual consta de varias partes:
<ul>
<li>La función wrap.</li>
<li>Configuración del proyecto y tareas.</li>
<li>Carga de plugins.</li>
<li>Tareas personalizadas.</li>
</ul>
Un ejemplo del fichero puede ser tal y como se muestra a continuación:

<blockquote>
	<pre>
  module.exports = function(grunt) {
  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),
    jshint: {
      files: ['Gruntfile.js', 'src/**/*.js', 'test/**/*.js'],
      options: {
        globals: {
          jQuery: true
        }
      }
    },
    watch: {
      files: ['<%= jshint.files %>'],
      tasks: ['jshint']
    }
  });
  grunt.loadNpmTasks('grunt­contrib­jshint');
  grunt.loadNpmTasks('grunt­contrib­watch');
  grunt.registerTask('default', ['jshint']);
};


	</pre>
</blockquote>

##Función wrapper

Dentro de esta función debe estar todo el código de configuración de Grunt.

>module.exports = function(grunt) {}

##Configuración del proyecto y tareas

En este caso dos tareas que se obtiene la meta información del fichero “package.json”, por otro lado también podemos definir la configuración de cada tarea.

En el caso particular del plugin de “jshint” no hace falta redifinirlo.
<blockquote>
	<pre>
  grunt.initConfig({
  pkg: grunt.file.readJSON('package.json'),
  jshint: {
    files: ['Gruntfile.js', 'src/**/*.js', 'test/**/*.js'],
    options: {
      globals: {
        jQuery: true
      }
    }
  },
  watch: {
    files: ['<%= jshint.files %>'],
    tasks: ['jshint']
  }
});	</pre>
</blockquote>



##Carga de plugins

A continuación, en esta sección habilitamos los plugins que hayamos instalado mediante npm install, en el caso de “jshint”

<blockquote>
	<pre>
//carga el plugin de la tarea jshint
npm install grunt­contrib­jshint –save­dev
</pre>
</blockquote>

Para ello ponemos en el fichero GruntFile lo siguiente:

>grunt.loadNpmTasks('grunt­contrib­jshint');

##Tareas Personalizadas

En esta sección se hace referencia a las tareas que posteriormente podremos invocar desde linea de comandos.

La principal tarea por definir es la por defecto “default”.

>grunt.registerTask('default', ['uglify']);

así escribiendo “grunt” en la linea de comandos ejecutaremos la tarea “uglify”.

De esta forma podremos definir mas tareas y asignarles una lista definida anteriormente en nuestro fichero, de tal manera que se ejecuten con tan sólo escribir el nombre de esa tarea.

>grunt.registerTask('watch', ['jshint', 'watch']);

En este caso ejecutaremos la tarea “watch”, la cual además de prevenir errores de código, también nos muestra si algún fichero ha sufrido algún cambio.

Espero que esta introducción os sirva para que empecéis a usar Grunt,

Un saludo,


Este mismo tutorial podéis verlo en <strong> <a href="http://www.phonegapspain.com/tutorial/introduccion-a-grunt-the-javascript-task-runner/">phoneGapSpain</a></strong>
