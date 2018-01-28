---
layout: post
title: Introducción a Vue.JS
date: 2017-09-12 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: vuelogo.png # Add image post (optional)
tags: [Holidays, Hawaii]
---
Hola a tod@s, ya hace tiempo de mi último tutorial, y en este caso os quería presentar Vue.JS y ver algún ejemplo que pueda ayudar a su explicación.

Vue.JS es un framework progresivo para la creación de interfaces de usuario que se centra sólo en la capa de vista y es muy fácil de integrar con otras librerías o proyectos existentes.

Vue.JS implementa el patrón MVVM, de tal manera que nos ahorra código, ya que refresca automáticamente los datos, ya que si la vista actualiza un dato que está presentando se actualiza el modelo automáticamente y viceversa, esto es lo que denominamos data binding.

Algunas de las características más importantes de Vue.JS son :

## Directivas
Administra los datos y la entrada del usuario con la vista. Entre las directivas más destacadas están: v-if, v-else-if, v-else o v-for

Un ejemplo de la forma en la cual usar esta directiva sería:


<div style="width:100%;margin-top:34px;">	
		<img src="/assets/img/vuejs-1.png" alt="vuejs-1"/>	
</div>


## Propiedades “computed” y “watch”

Con las propiedades “computed”, puede renderizar datos complejos que se calculan a partir de otros datos, VueJS se ocupará automáticamente de todas las dependencias. Para ello solo hay que añadir el objeto “Computed” a la vista, dentro de este objeto sólo podrá haber funciones, de manera que se ejecutará de forma automática los cambios a los datos cuando se visualice la vista.

Por otro lado con la propiedad “watch”, también se define como objeto, para ello hay que definir la propiedad que queremos observar, para luego definir una función que involucre a la propiedad descrita anteriormente.


## Componentes Modulares

Son muy útiles a la hora de reutilizar código.Es necesario describir todos las propiedades y eventos asociados a dicho componente. Para declarar un componente hay que ubicarlo en la carpeta components con la extensión “.vue” , para nuestro caso definiremos un componente llamado “Ejemplo.Vue”



<div style="width:100%;margin-top:34px;">	
		<img src="/assets/img/vuejs-2.png" alt="vuejs-2"/>	
</div>

Luego para poder usar este nuevo componente, solo basta con insertarlo en el fichero y principal, en nuestro caso en el main.js

<div style="width:100%;margin-top:34px;">	
		<img src="/assets/img/vuejs-3.png" alt="vuejs-3"/>	
</div>

En el caso de que usemos el mismo componente, estos se crearán de forma separada de tal manera que cada uno tendrá su foco.

En conclusión, yo diría que VueJS, tiene una curva de aprendizaje menor que la de sus adversarios (Angular y React), por otro lado posee un peso muy ligero, y ademas es mas rápido que ReactJS. Por todo esto hace que sea un framework que está teniendo una alta aceptación en la comunidad y por tanto hay que tenerlo en cuenta a la hora de desarrollar nuestros proyectos.

Espero que os parezca interesante y que os animéis con Vue.JS 

Este mismo tutorial podéis verlo en <strong> <a href="http://www.phonegapspain.com/tutorial/introduccion-a-vue-js/">phoneGapSpain</a></strong>