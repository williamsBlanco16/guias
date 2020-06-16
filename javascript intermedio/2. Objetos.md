## **Chapter 2** – Objetos, un buen punto de partida 

En la web es común encontrar la expresión “todo en JavaScript es un objeto” esto aunque no es cierto funciona muy bien como recurso pedagógico. Ver todo en javascript como un objeto simplifica el aprendizaje, sin embargo una expresión más acertada seria.
>.“En javascript casi todo se comporta como un objeto”. 

Por otra parte no queda duda que los objetos son una parte fundamental para mejorar nuestros skills como desarrolladores JS y por ende un buen punto de partida.

***

### Abordemos el tema desde el principio

Un objeto es un conjunto de propiedades definidas como **key:value** el dinamismo de javascript permite que el value sea un tipo de dato primitivo, una función u otro objecto.

Tenemos tres caminos comunes para crear objectos:

``` js
  //creando objetos
  const objetA = {} //forma literal
  const objetB = new Object() //constructor
  const objetC = Object.create(Object.prototype) //usando Object.create
```

Tenemos cinco caminos comunes para agregar propiedades a un objeto:

```js
 //Creando propiedades

 //Al momento de la definicion literal
 const character = {
   name : "Luke",
   homeWorld: "Tatooine",
   greet: () => "Hola soy Luke Skywalker"
 };

 //usando el operador punto (.)
 character.gender = "male"

 //usando el operador []
 character["eye_color"] = "blue"

 //usando el metodo Object.defineProperty
 Object.defineProperty(character,"hair_color",{
   value:"blond",
   writable:true,
   configurable:true,
   enumerable:true
 });

 //usando el metodo Object.defineProperties
 Object.defineProperties(character,{
   "specie":{
     value:"human",
   },
   "vehicles":["Snowspeeder","Imperial Speeder Bike"]
 });
```

la creación de propiedades a través de los métodos estáticos __[Object.defineProperty](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Object/defineProperty)__  y  __[Object.defineProperties](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Object/defineProperties)__  tienen como principal características diferenciadora la posibilidad de
Configurar 3 propiedades que tienen false como valor por defecto:

+ **writable** : Posibilidad de actualizar el value a traves del operador asignación.

+ **configurable**: posibilidad de eliminar la propiedad a traves del operador delete.

+ **enumerable**: posibilidad de visualizar la propiedad durante su enumeracion.

Al colocar estas propiedades en true obtendremos el mismo comportamiento que se logra al asignar propiedades por los otros métodos mencionados.

Finalmente las propiedades creadas pueden ser eliminadas (siempre que no se haya configurado configurable:false)  a través del operador **delete** 

```js
  //Eliminando propiedad
  delete character.greet;
  delete character["eye_color"];
```

>“... Y de qué sirve un libro sin dibujos ni diálogos? ” – fragmento  Alicia en el país de las maravillas