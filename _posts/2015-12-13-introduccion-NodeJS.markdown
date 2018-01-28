---
layout: post
title: Introducción a Node.JS
date: 2015-12-13 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img:  nodejs.png # Add image post (optional)
tags: [Holidays, Hawaii]
---
Hola a todos, en este tutorial quiero haceros una introducción a NodeJS, seguramente hayáis oído hablar de él, NodeJS viene del core de Chrome. Lo primero que vamos a hacer es instalarlo, desde su web, más concretamente la versión v4.1.1

Una vez instalado, abriremos una consola y ejecutaremos:

>node -v


Así comprobaremos que lo tenemos instalado correctamente, por lo que debería mostrarnos “v4.1.1”.
A continuación escribiremos:

>node


De tal manera que podremos escribir algo tal que console.log(“Hola Mundo”);
Esto devolverá dos líneas, la primera sería el mensaje en si “Hola Mundo”, y la segunda el valor que devuelve. En éste caso, al ser log un “statement” no devuelve nada, por lo que nos mostrará ‘undefined‘.

Por el contrario, podemos ejecutar este otro código:
<blockquote>
<pre><code>
function sum(a ,b){return a+b}
undefined
sum(2,3)
5
</code>
</pre>
</blockquote>


Como podemos comprobar, con NodeJS podemos ejecutar código javascript para poder comprobar el comportamiento del mismo sin tener que ejecutarlo desde una página html, por tanto, NodeJS no es sólo un servidor web, sino que es más que eso, más adelante os mostraré cómo se crea un servidor web con NodeJS.

Otras de las opciones que ofrece NodeJS es que podemos escribir en un fichero de texto directamente.


> echo “console.log(“Hola, Estoy escribiendo/leyendo de un fichero :D ”);”  >  file.js

Luego, sólo tenemos que ubicarnos donde se encuentre el fichero y ejecutar:

>node file.js

Mostrando como resultado:

>“Hola, estoy escribiendo/leyendo de un fichero :D”

Para comprobar el resultado escrito en el fichero ejecutamos

>cat file.js


##Utilidades a destacar de la API

Quiero destacaros algunas de las utilidades que ofrece la API.

#Events

En el caso de que queramos lanzar eventos, todos son instancias de Events.EventEmitter, a los que podemos acceder mediante require(“events”)

De tal manera que sólo tenemos que acceder usando:

>var EventEmitter = require('events').EventEmitter

Para ello, vamos a crear un fichero llamado nodeEvents.js, donde declararemos la instancia y definiremos un listener para lanzar el mismo, de tal manera que el contenido sería el siguiente:
<blockquote>
<pre>
var EventEmitter = require('events').EventEmitter
var ee = new EventEmitter();
ee.on('AlgunEvento',function(data){
    console.log('Algun evento' , data);
});
ee.emit('AlgunEvento',{option:true, title : ' Evento Lanzado'});
</pre>
</blockquote>

A continuación ejecutamos en la línea de comandos:

>node nodeEvents.js

El cual nos mostrará el siguiente resultado:

>Algún Evento { option:true, title: 'Evento Lanzado' }

Por lo que realmente se ha lanzado el evento y ha sido escuchado.

<div style="width:100%;margin-top:34px;">	
		<img src="/assets/img/captura-tutorial-node.png" alt="vuejs-2"/>	
</div>

#Utilities

Otra funcionalidad que posee NodeJS es el módulo ‘util‘, el cual puede ser de gran utilidad, destacaría la función util.debuglog(section), con la cual podremos hacer debug, pero sólo lo que nos interese mostrar. Para ello definiremos antes:

>var foo = util.debuglog('foo');

Para luego poder usarlo de ésta manera:

>foo('Node es genial!”');

Y para ejecutarlo habrá que usar NODE_DEBUG seguido de section, en este caso “foo” tal que así NODE_DEBUG=foo, de tal manera que el resultado será:

>“Node es genial!”

Por otro lado, se pueden definir varios debuglog a la vez, para lo que solo bastará con ponerlos en una lista separadas con comas, es decir, NODE_DEBUG=foo,bar

<blockquote>
<pre>
var foo = util.debuglog('foo')
var bar = util.debuglog('bar')
foo("Node es genial!")
bar("Node es increible!")
</pre>
</blockquote>

E invocar de la siguiente manera NODE_DEBUG=foo,bar node utilNode.js


<div style="width:100%;margin-top:34px;">	
		<img src="/assets/img/captura-tutorial-node2.png" alt="vuejs-2"/>	
</div>



#OS

Otra utilidad a destacar seria el modulo OS, con el cual se puede obtener información del sistema operativo, para ello sólo debemos acceder mediante require(‘os’), algunas de las utilidades puede ser por ejemplo saber:

• La arquitectura de la CPU os.arch();
• La plataforma del sistema operativo os.platform();
• La memoria libre os.freemem();

#HTTP

Una de las funcionalidades mas destacadas de NodeJS, y la más conocida, es como servidor web, para ello debemos usar el módulo http, para lo cual usamos require(‘http’). Con el que podemos crear un servidor web en pocas líneas, para ello crearemos un fichero llamado servidorNode.js:


<blockquote>
<pre><code>

var http = require('http')
var server = http.createServer(function(request,response){
  response.write("&lt;h1&gt;Hola!&lt;/h1&gt;&lt;p&gt;esto es un servidor NodeJS&lt;/p&gt;");
  response.end();
});
server.listen(3000);

</code></pre>
</blockquote>



Así, en línea de comando sólo tendremos que ejecutar:

>node servidorNode.js

A continuación, tendremos que abrir el navegador y escribir localhost:3000.

Por último quiero hablaros de NPM, el cual es “Node Package Manager”, código hecho por terceros y que se comparte para poder ser usado por el resto. En este caso podemos echar un vistazo a los existentes en la siguiente web https://www.npmjs.com/
Para usar NPM en NodeJS podemos ejecutar.

>npm

<div style="width:100%;margin-top:34px;">	
		<img src="/assets/img/captura-tutorial-node3.png" alt="vuejs-2"/>	
</div>


Donde obtendremos una lista con los comandos que podemos usar, de tal manera que para instalar uno nuevo deberemos usar:

>npm install <paquete>

Espero que os sirva este tutorial de introducción a NodeJS, y empecéis a usarlo.

Un saludo.

Este mismo tutorial podéis verlo en <strong> <a href="http://www.phonegapspain.com/tutorial/introduccion-a-nodejs/">phoneGapSpain</a></strong>
 

