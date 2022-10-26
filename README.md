# repasoJSFundamentals



### Ejercicio 1

Teniendo dos arrays con valores individuales, escriba un programa de JavaScript para calcular la suma de cada valor de cada índice individual de los arrays dados.

Ejemplo de arrays :   
```js
array1 = [1,0,2,3,4];  
array2 = [3,5,6,7,8,13];
```

Output :  
```js
[4, 5, 8, 10, 12, 13]
```
<summary></summary>

<details><summary>Respuesta - ¡Haz Click!</summary>


```js

function Arrays_sum(array1, array2) 
{
  var result = [];
  var ctr = 0;
  var x=0;

  if (array1.length === 0) 
   return "array1 is empty";
  if (array2.length === 0) 
   return "array2 is empty";   

 while (ctr < array1.length && ctr < array2.length) 
  {
    result.push(array1[ctr] + array2[ctr]);
    ctr++;
  }

 if (ctr === array1.length) 
 {
    for (x = ctr; x < array2.length; x++)   {
      result.push(array2[x]);
    }
  } 
  else
  {
  for (x = ctr; x < array1.length; x++) 
    {
      result.push(array1[x]);
    }
  }
  return result;
}

console.log(Arrays_sum([1,0,2,3,4], [3,5,6,7,8,13]));

//[4,5,8,10,12,13]
```


Versión ES6
```js

function Arrays_sum(array1, array2) 
{
  const result = [];
  let ctr = 0;
  let x=0;

  if (array1.length === 0) 
   return "array1 is empty";
  if (array2.length === 0) 
   return "array2 is empty";   

 while (ctr < array1.length && ctr < array2.length) 
  {
    result.push(array1[ctr] + array2[ctr]);
    ctr++;
  }

 if (ctr === array1.length) 
 {
    for (x = ctr; x < array2.length; x++)   {
      result.push(array2[x]);
    }
  } 
  else
  {
  for (x = ctr; x < array1.length; x++) 
    {
      result.push(array1[x]);
    }
  }
  return result;
}

console.log(Arrays_sum([1,0,2,3,4], [3,5,6,7,8,13]));

```
</details>


### Ejercicio 2

Escribe un programa en JavaScript para calcular la unión de dos arrays

Ejemplo:  

```js
console.log(union([1, 2, 3], [100, 2, 1, 10]));  
```

Output:
```js
 [1, 2, 3, 10, 100]
```

<details><summary>Respuesta - ¡Haz Click!</summary>


```js
function union(arra1, arra2) {
  
  if ((arra1 == null) || (arra2==null)) 
    return void 0;
  
  var obj = {};
 
  for (var i = arra1.length-1; i >= 0; -- i)
     obj[arra1[i]] = arra1[i];
 
  for (var i = arra2.length-1; i >= 0; -- i)
     obj[arra2[i]] = arra2[i];
 
  var res = [];
 
  for (var n in obj)
  {
  
    if (obj.hasOwnProperty(n)) 
      res.push(obj[n]);
  }
 
  return res;
}
console.log(union([1, 2, 3], [100, 2, 1, 10]));

// [1,2,3,10,100]
```
</details>


### Ejercicio 3

Escribe una función de JavaScript para encontrar las diferencia entre dos arrays.

Ejemplo: 
```js
console.log(difference([1, 2, 3], [100, 2, 1, 10]));   
// ["3", "10", "100"]  
console.log(difference([1, 2, 3, 4, 5], [1, [2], [3, [[4]]],[5,6]]));   
// ["6"]  
console.log(difference([1, 2, 3], [100, 2, 1, 10]));  
// ["3", "10", "100"]

```

<details><summary>Respuesta - ¡Haz Click!</summary>

```js
function differenceOf2Arrays (array1, array2) {
var temp = [];
array1 = array1.toString().split(',').map(Number);
array2 = array2.toString().split(',').map(Number);

for (var i in array1) {
if(array2.indexOf(array1[i]) === -1) temp.push(array1[i]);
}
for(i in array2) {
if(array1.indexOf(array2[i]) === -1) temp.push(array2[i]);
}
return temp.sort((a,b) => a-b);
}

console.log(differenceOf2Arrays([1, 2, 3], [100, 2, 1, 10]));
console.log(differenceOf2Arrays([1, 2, 3, 4, 5], [1, [2], [3, [[4]]],[5,6]]));

// [3,10,100]
// [6]

```
</details>


### Ejercicio 4

Escriba un programa de JavaScript para mostrar el estado de la lectura (es decir, mostrar el nombre del libro, el nombre del autor y el estado de la lectura) de los siguientes libros.
```js
let library = [ 
   {
       author: 'Bill Gates',
       title: 'The Road Ahead',
       readingStatus: true
   },
   {
       author: 'Steve Jobs',
       title: 'Walter Isaacson',
       readingStatus: true
   },
   {
       author: 'Suzanne Collins',
       title:  'Mockingjay: The Final Book of The Hunger Games', 
       readingStatus: false
   }];

```

<details><summary>Respuesta - ¡Haz Click!</summary>

```js
for (var i = 0; i &lt; library.length; i++) 
   {
    var book =` ' ${library[i].title}  '  by  ${library[i].author}  .`;
    if (library[i].readingStatus) {
      console.log(`Already read " ${book}`);
    } else
    {
     console.log(`You still need to read ${book}`);
    }
   }
// Already read 'Bill Gates' by The Road Ahead.
// Already read 'Steve Jobs' by Walter Isaacson.
// You still need to read 'Mockingjay: The Final Book of The Hunger Games' by Suzanne Collins.
```

</details>


### Ejercicio 5

Escriba una función JavaScript para comprobar si un "input" es un string o no.

Ejemplo: 

```js
console.log(is_string('w3resource'));   
true  
console.log(is_string([1, 2, 4, 0]));  
false
```

<details><summary>Respuesta - ¡Haz Click!</summary>

```js

is_string = function(input) {
  if (Object.prototype.toString.call(input) === '[object String]')
    return true;
  else
    return false;   
    };
console.log(is_string('w3resource')); // true
console.log(is_string([1, 2, 4, 0])); // false

```
</details>


### Ejercicio 5

Escribe una función de JavaScript que concatene un string dado n veces (por defecto es 1).

Ejemplo: 

```javascript
console.log(repeat('Ha!'));   
console.log(repeat('Ha!',2));   
console.log(repeat('Ha!',3));  
// "Ha!"   
// "Ha!Ha!"   
// "Ha!Ha!Ha!"
```

<details><summary>Respuesta - ¡Haz Click!</summary>+

```js
repeat = function repeat(str, count) {
    if(typeof(count) == "undefined") {
    count =1;
  }
  return count &lt; 1 ? '' : new Array(count + 1).join(str);
    }
console.log(repeat('Ha!'));
console.log(repeat('Ha!',2));
console.log(repeat('Ha!',3));
```
</details>


