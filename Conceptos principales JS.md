# *Conceptos principales de JS*
## Tipos de datos:
### **Primitivos:** *Se accede directamente al valor*.
- string
- number
- boolean
- null
- undefined
- NaN
### **Compuestos:** *Se accede a la referencia del valor*.

- object = {}
- array = []
- function () { }
- Class {}
- etc.

## Strings 
Los strings son cadenas de texto y tienen propiedades y métodos importantes a continuación las principales.

### Propiedades
- `length` : Devuelve la longitud de una cadena de texto.
### Métodos 
- `toUpperCase()` : Convierte una cadena de texto a mayúsculas.
- `toLowerCase()` : Convierte una cadena de texto a minúsculas.
- `substring()` : Devuelve una subcadena de una cadena de texto.
- `split()` : Divide una cadena de texto en un array de subcadenas utilizando un delimitador específico.
- `replace()` : Reemplaza una subcadena de una cadena de texto con otra subcadena.

*A continuacion ejemplos de sus usos:*

```javascript
// Usando métodos y propiedades de los string

    let soyUnString = "Hola Soy El Texto de Prueba";

    console.log(soyUnString.length);                //27

    console.log(soyUnString.toUpperCase());         // "HOLA SOY EL TEXTO DE PRUEBA"

    console.log(soyUnString.toLowerCase());         //"hola soy el texto de prueba" 

    console.log(soyUnString.substring(0,8));        //"Hola Soy"
    console.log(soyUnString.substring(8,0));        //"Hola Soy"
    console.log(soyUnString.substring(8,27));       //" El Texto de Prueba"

    console.log(soyUnString.split());               // ["Hola Soy El Texto de Prueba"]
    console.log(soyUnString.split(" "));            //["Hola", "Soy", "El", "Texto", "de", "Prueba"]
    console.log(soyUnString.split(" ",3));          //["Hola", "Soy", "El"]

    console.log(soyUnString.replace("Hola","Bye"));     // "Bye Soy El Texto de Prueba"
```
#### TEMPLATE STRINGS

El principal uso de las template strings es la creación de cadenas de texto con valores dinámicos, es decir, donde se requiere que algunos fragmentos de la cadena varíen en función de datos proporcionados en tiempo de ejecución.

*Ejemplo de uso:*

```javascript
    const nombre = "Juan";
    const edad = 30;
    const ciudad = "Madrid";

    const mensaje = `Hola, mi nombre es ${nombre}, tengo ${edad} años y vivo en ${ciudad}.`;
    console.log(mensaje);                          

    // retorna 
    Hola, mi nombre es Juan, tengo 30 años y vivo en Madrid.
```

# FUNCIONES EN JS
En JavaScript, una función es un bloque de código que se puede llamar y ejecutar varias veces en diferentes partes de un programa. Las funciones permiten escribir código reutilizable, modular y organizado, lo que hace que el código sea más fácil de mantener y actualizar.

*Existen varios tipos de funciones en JavaScript:*
- **Funciones declarativas o function statements:**  

    *Son las funciones más comunes y se definen utilizando la palabra clave `function`, seguida por el nombre de la función, los parámetros que recibe y el cuerpo de la función que contiene las instrucciones a ejecutar.*

    ```javascript
        // Ejemplo de función declarativa
        function sumar(a, b) {
            return a + b;
        }

        // Llamando a la función
        let resultado = sumar(2, 3);
        console.log(resultado); // salida: 5
    ```
- **Funciones expresivas o function expressions:** 

    *Son funciones que se definen como expresiones y se asignan a una variable o constante. Este tipo de funciones no tienen nombre y se pueden pasar como argumentos a otras funciones.*

    ```javascript 
        // Ejemplo de función expresiva
        const multiplicar = function(a, b) {
            return a * b;
        }

        // Llamando a la función
        let resultado = multiplicar(2, 3);
        console.log(resultado); // salida: 6
    ```
- **Funciones de flecha o arrow functions:** 

    *Son una forma más breve y concisa de definir funciones expresivas y se utilizan principalmente en operaciones de map, filter y reduce en arrays. Se definen utilizando la sintaxis `() => {}` y no tienen su propio objeto `this`, lo que puede hacer que sean más seguras y predecibles en algunos casos.*

    ```javascript 
        // Ejemplo de función de flecha
        const dividir = (a, b) => {
            return a / b;
        }

        // Llamando a la función
        let resultado = dividir(10, 2);
        console.log(resultado); // salida: 5
    ```
- **Métodos de objeto:** 

    *Son funciones que están definidas dentro de objetos y se llaman utilizando la sintaxis `objeto.nombreFuncion()`.*

    ```javascript
        // Ejemplo de método de objeto
        const persona = {
            nombre: "Juan",
            edad: 30,
            saludar: function() {
            console.log(`Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`);
        }
        }

        // Llamando al método de objeto
        persona.saludar(); // salida: Hola, mi nombre es Juan y tengo 30 años.
    ```

## Diferencias entre funciones declaradas y expresadas

Las funciones declaradas y las funciones expresadas son dos formas diferentes de definir funciones en JavaScript. Aunque ambas formas hacen lo mismo, que es definir una función, existen algunas diferencias importantes entre ellas.

- **Como se definen:** 

    *Las funciones declaradas se definen utilizando la palabra clave `function` seguida por el nombre de la función y los parámetros que recibe. Por otro lado, las funciones expresadas se definen utilizando una asignación, donde el valor de la asignación es una función anónima.*

    ```javascript
        <!-- funcion declarada -->
        function sumar(a, b) {
            return a + b;
        }

        <!-- funcion expresada -->
        const sumar = function(a, b) {
            return a + b;
        }
    ```
- **Hoisting:** 

    *Las funciones declaradas son "elevadas" o "levantadas" al inicio del ámbito en el que se encuentran, lo que significa que se pueden llamar a la función antes de que se declare en el código. En cambio, las funciones expresadas no son elevadas, por lo que solo se pueden llamar después de que se haya declarado.*

- **Nombre de la función** 

    *Las funciones declaradas tienen un nombre que se puede utilizar para llamar a la función dentro del ámbito en el que se definen. Por otro lado, las funciones expresadas no tienen un nombre propio y solo se pueden llamar a través de la variable a la que se asignan.*

    ```javascript
    function sumar(a, b) {
        return a + b;
    }

    console.log(sumar(2, 3)); // salida: 5
    ```

# ARRAYS EN JS
Los arrays son una de las estructuras de datos más importantes en JavaScript y se utilizan para almacenar una colección de elementos. Los elementos pueden ser de cualquier tipo de datos, incluyendo números, cadenas, booleanos, objetos, funciones y otros arrays.

Para crear un array en JavaScript, puedes utilizar la siguiente sintaxis: 

    const miArray = [elemento1, elemento2, elemento3, ...];

Donde `miArray` es el nombre del array y `elemento1`, `elemento2`, `elemento3`, etc., son los elementos que se van a almacenar en el array. También puedes crear un array vacío simplemente utilizando `[]`.

- Los arrays en JavaScript son dinámicos, lo que significa que pueden crecer o reducir su tamaño a medida que se añaden o eliminan elementos. Para añadir un elemento al final del array, puedes utilizar el método `push()`:

``` javascript
    const miArray = [1, 2, 3];
    miArray.push(4);
    console.log(miArray); // salida: [1, 2, 3, 4]
```
- Para eliminar el último elemento del array, puedes utilizar el método `pop()`:

```javascript

    const miArray = [1, 2, 3, 4];
    miArray.pop();
    console.log(miArray); // salida: [1, 2, 3]
```
- También puedes añadir o eliminar elementos de cualquier posición del array utilizando los métodos `splice()` y `slice()`. Por ejemplo, para añadir un elemento en la segunda posición del array:

```javascript

    const miArray = [1, 2, 3];
    miArray.splice(1, 0, 4);
    console.log(miArray); // salida: [1, 4, 2, 3]
```
*En este ejemplo, **el primer argumento `1` indica la posición en la que se va a añadir el elemento (en este caso, la segunda posición), el segundo argumento `0` indica que no se van a eliminar elementos y el tercer argumento `4` es el elemento que se va a añadir.***

- Para eliminar elementos de una posición determinada del array, puedes utilizar el método splice() con un segundo argumento diferente de 0. Por ejemplo, para eliminar el segundo elemento del array:

```javascript

    const miArray = [1, 2, 3];
    miArray.splice(1, 1);
    console.log(miArray); // salida: [1, 3]
```    
*En este ejemplo, **el primer argumento `1` indica la posición del elemento que se va a eliminar y el segundo argumento `1` indica que solo se va a eliminar un elemento**.*

# OBJETOS EN JAVASCRIPT

En JavaScript, un objeto es una colección de propiedades que se utilizan para describir un elemento. Cada propiedad se compone de una clave y un valor, y pueden ser de diferentes tipos, como cadenas de texto, números, booleanos, funciones y otros objetos.

Los objetos en JavaScript se crean utilizando una sintaxis de llaves (`{}`) y se pueden acceder a las propiedades utilizando la notación de punto (`.`) o la notación de corchetes (`[]`).

## Creación de objetos
Hay varias maneras de crear objetos en JavaScript. A continuación, se presentan algunos ejemplos:

- **Literal de objeto:** 

    *El literal de objeto es la forma más común de crear un objeto en JavaScript. Para crear un objeto mediante un literal, simplemente se utilizan llaves `{}` y se especifican las propiedades:*

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };
    ```
- **Constructor de objeto:* 

    *También se pueden crear objetos utilizando un constructor de objeto. Un constructor de objeto es una función que se utiliza para crear objetos. Se puede utilizar la palabra clave "new" para crear una nueva instancia del objeto:*

    ```javascript
    function Objeto(propiedad1, propiedad2, propiedad3) {
      this.propiedad1 = propiedad1;
      this.propiedad2 = propiedad2;
      this.propiedad3 = propiedad3;
    }
    
    const objeto = new Objeto(valor1, valor2, valor3);
    ```
- **Object.create()**

    *La función Object.create() es otra forma de crear objetos en JavaScript. Esta función toma un objeto como argumento y devuelve un nuevo objeto con el objeto especificado como prototipo:*

    ```javascript
    const objetoPrototipo = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };

    const objeto = Object.create(objetoPrototipo);
    ```

## Acceso a propiedades de objetos
Una vez que se ha creado un objeto, se puede acceder a las propiedades del objeto utilizando la notación de punto o la notación de corchetes.

- **Notación de punto**

    *La notación de punto se utiliza para acceder a las propiedades de un objeto mediante el nombre de la propiedad:*

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };

    console.log(objeto.propiedad1); // Imprime valor1
    ```
- **Notación de corchetes**

    *La notación de corchetes se utiliza para acceder a las propiedades de un objeto mediante una cadena de texto que representa el nombre de la propiedad:*

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };

    console.log(objeto['propiedad2']); // Imprime valor2
    ```
- ***Métodos de objetos***

    Los métodos son funciones que se definen dentro de un objeto y se utilizan para realizar una tarea específica en el objeto. Para definir un método, se puede utilizar la sintaxis de función dentro del objeto:

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3,
      metodo: function() {
        // Código del método
      }
    };
    ```
- **Modificación de propiedades de objetos**

    Para modificar una propiedad de un objeto, simplemente se asigna un nuevo valor a la propiedad:

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };

    objeto.propiedad2 = nuevoValor;
    ```
- **Eliminación de propiedades de objetos**

    Para eliminar una propiedad de un objeto, se utiliza la palabra clave "delete":

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };

    delete objeto.propiedad2;
    ```
- **Iteración de propiedades de objetos**

    Para iterar sobre las propiedades de un objeto, se pueden utilizar los bucles "for...in". Estos bucles recorren todas las propiedades enumerables de un objeto, incluyendo las propiedades heredadas del prototipo:

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };

    for (const propiedad in objeto) {
      console.log(propiedad, objeto[propiedad]);
    }
    ```
### Métodos útiles de objetos
JavaScript proporciona varios métodos útiles para trabajar con objetos.

- **`Object.keys()`**

    El método `Object.keys()` devuelve un array de las claves de un objeto:

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };

    const claves = Object.keys(objeto); // Retorna ['propiedad1', 'propiedad2', 'propiedad3']
    ```
- **`Object.values()`**
    
    El método `Object.values()` devuelve un array de los valores de un objeto:

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };

    const valores = Object.values(objeto); // Retorna [valor1, valor2]
    ```

- **`Object.entries()`**

    El método `Object.entries()` devuelve un array de arrays donde cada uno contiene una clave y un valor del objeto:

    ```javascript
    const objeto = {
      propiedad1: valor1,
      propiedad2: valor2,
      propiedad3: valor3
    };

    const entradas = Object.entries(objeto); // Retorna [['propiedad1', valor1], ['propiedad2', valor2], ['propiedad3', valor3]]

    ```

- **Object.assign()**

    El método `Object.assign()` copia las propiedades de uno o más objetos en otro objeto. Si una propiedad ya existe en el objeto de destino, se sobrescribe con la propiedad del objeto fuente:

    ```javascript
    const objeto1 = {
    propiedad1: valor1,
    propiedad2: valor2,
    propiedad3: valor3
    };

    const objeto2 = {
    propiedad2: nuevoValor,
    propiedad4: valor4
    };

    Object.assign(objeto1, objeto2); // La propiedad2 en objeto1 se sobrescribe con nuevoValor y se agrega propiedad4
    ```
# BREAK Y CONTINUE

"break" y "continue" son palabras clave que se utilizan en JavaScript para controlar el flujo de los bucles.

1. **Break:** 

    La palabra clave "break" se utiliza para salir de un bucle de forma prematura. Por ejemplo, si estamos iterando un array con un bucle "for" y queremos salir del bucle cuando se encuentra un elemento en particular, podemos hacer lo siguiente:

    ```javascript
    Copy code
    const array = [1, 2, 3, 4, 5];
    for (let i = 0; i < array.length; i++) {
    if (array[i] === 3) {
        break;
    }
    console.log(array[i]);
    }
    ```
    En este ejemplo, el bucle se detendrá cuando se encuentre el número 3 en el array.

2. **Continue:** 

     La palabra clave "continue" se utiliza para saltar una iteración en un bucle y pasar a la siguiente. Por ejemplo, si estamos iterando un array con un bucle "for" y queremos omitir un elemento en particular, podemos hacer lo siguiente:
    ```javascript
    Copy code
    const array = [1, 2, 3, 4, 5];
    for (let i = 0; i < array.length; i++) {
      if (array[i] === 3) {
        continue;
      }
      console.log(array[i]);
    }
    ```
    En este ejemplo, la iteración se saltará cuando se encuentre el número 3 en el array y pasará directamente al siguiente elemento.

***Es importante tener en cuenta que tanto "break" como "continue" sólo se aplican al bucle más cercano en el que están incluidos. Si hay bucles anidados, sólo afectarán al bucle más cercano.***

# DESTRUCTURACION

La destructuración es una característica de JavaScript que permite extraer valores de objetos y arrays y asignarlos a variables individuales. Esta característica es especialmente útil cuando trabajamos con datos estructurados y queremos acceder a propiedades específicas de un objeto o a elementos específicos de un array.

1. **Destructuración de objetos:** 
    La destructuración de objetos nos permite extraer valores de propiedades específicas de un objeto y asignarlos a variables individuales. Por ejemplo:

    ```javascript
    const persona = { 
        nombre: 'Juan', 
        edad: 30, 
        ciudad: 'Buenos Aires' };

    const { nombre, edad } = persona;
    console.log(nombre); // 'Juan'
    console.log(edad); // 30
    ```

    *En este ejemplo, hemos creado un objeto llamado "persona" con tres propiedades. Luego, hemos utilizado la sintaxis de destructuración para extraer las propiedades "nombre" y "edad" y asignarlas a variables individuales.*

- También podemos utilizar alias para las variables, en caso de que queramos utilizar un nombre diferente al de la propiedad del objeto:

    ```javascript
    const { nombre: personaNombre, edad: personaEdad } = persona;
    console.log(personaNombre); // 'Juan'
    console.log(personaEdad); // 30
    ```
    En este ejemplo, hemos utilizado la sintaxis de destructuración con alias para asignar los valores de las propiedades del objeto a variables con diferentes nombres.

- **Destructuración de arrays:** 

    La destructuración de arrays nos permite extraer elementos específicos de un array y asignarlos a variables individuales. Por ejemplo:

    ```javascript
    const numeros = [1, 2, 3, 4, 5];
    const [primerNumero, segundoNumero] = numeros;
    console.log(primerNumero); // 1
    console.log(segundoNumero); // 2
    ```
    *En este ejemplo, hemos creado un array llamado "numeros" con cinco elementos. Luego, hemos utilizado la sintaxis de destructuración para extraer los primeros dos elementos del array y asignarlos a variables individuales.*

- *También podemos utilizar el operador "rest" para extraer los elementos restantes de un array y asignarlos a una variable:*

    ```javascript
    const [primerNumero, segundoNumero, ...restoDeNumeros] = numeros;
    console.log(primerNumero); // 1
    console.log(segundoNumero); // 2
    console.log(restoDeNumeros); // [3, 4, 5]
    ```
    *En este ejemplo, hemos utilizado la sintaxis de destructuración con el operador "rest" para extraer los primeros dos elementos del array y asignarlos a variables individuales, y luego hemos asignado el resto de los elementos a la variable "restoDeNumeros".*

- **Destructuración anidada:** 

    También podemos utilizar la destructuración anidada para extraer valores de objetos y arrays anidados. Por ejemplo:

    ```javascript
    const persona = { 
        nombre: 'Juan', 
        edad: 30, 
        direccion: { 
            calle: 'Av. Rivadavia', 
            numero: 123 } 
        };

    const { nombre, edad, direccion: { calle, numero } } = persona;

    console.log(nombre); // 'Juan'
    console.log(edad); // 30
    console.log(calle); // 'Av. Rivadavia'
    console.log(numero); // 123
    ```
    *En este ejemplo, hemos utilizado la sintaxis de destructuración anidada para extraer los valores de las propiedades "nombre", "edad", "calle" y "numero"de un objeto anidado.*

- **Destructuración en parámetros de funciones:** 

    También podemos utilizar la destructuración en los parámetros de una función para extraer los valores de un objeto o un array pasado como argumento. Por ejemplo:

    ```javascript
    
    function imprimirPersona({ nombre, edad }) {
      console.log(`La persona se llama ${nombre} y tiene ${edad} años.`);
    }
    
    const persona = { nombre: 'Juan', edad: 30 };
    imprimirPersona(persona); // La persona se llama Juan y tiene 30 años.
    ```

    *En este ejemplo, hemos definido una función llamada "imprimirPersona" que recibe un objeto con dos propiedades: "nombre" y "edad". Luego, hemos utilizado la sintaxis de destructuración en los parámetros de la función para extraer los valores de esas propiedades del objeto que se pasa como argumento.*

- **Destructuración de valores por defecto:** 

    También podemos utilizar valores por defecto en la sintaxis de destructuración para asignar un valor a una variable en caso de que la propiedad del objeto o el elemento del array no exista. Por ejemplo:

    ```javascript

    const persona = { nombre: 'Juan', edad: 30 };

    const { nombre, edad, ciudad = 'Buenos Aires' } = persona;

    console.log(ciudad); // 'Buenos Aires'
    ```

    *En este ejemplo, hemos utilizado la sintaxis de destructuración con un valor por defecto para la propiedad "ciudad". Como la propiedad "ciudad" no existe en el objeto "persona", la variable "ciudad" se asigna al valor por defecto que hemos definido: "Buenos Aires".*


