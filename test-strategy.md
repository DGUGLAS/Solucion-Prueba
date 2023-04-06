# Documentacion

## Errores

Linea 50: El numero random esta retornando un numero decimal lo cual evita que el numero que el usuario ingrese coincida, por lo cual se debe se debe convertir a numero entero utilizando Math.floor().

Error.

````javascript
  let randomNumber = Math.random() * 10;```
````

Solucion.

```javascript
let randomNumber = Math.floor(Math.random() * 100 + 1);
```

Linea 51: Se require de 10 intentos y el programa actual solo permite 5 debido a que es el valor que tiene asignado en ATTEMPS, esto se resuelve cambiando el dato de 5 a 10.

Error.

```javascript
const ATTEMPS = 5;
```

Solucion.

```javascript
const ATTEMPS = 10;
```

Linea 54: Hace falta un ( . ) al inicio de LowOrHi por ende la clase no se esta mandando a llamar, se debe de agregar un ( . ) a lowOrHi para que pueda funcionar.

Error.

```javascript
const lowOrHi = document.querySelector("lowOrHi");
```

Solucion.

```javascript
const lowOrHi = document.querySelector(".lowOrHi");
```

Linea 64: Para mostrar una alerta al usuario y evitar que los intentos sigan incrementando al ingresesar datos distintos a numeros decidi utilizar una expresion regular que solo acepte numeros enteros del 1-9 haciendo un test en 'userGuess' que es el valor que el usuario ingresa. Se realiza una negacion, usando el operador ( '!' ) indicando que lo que el usuario ingreso no cumple con la expresion regular, por ende retorna una alerta y no siguen incrementando los instentos.

Solucion.

```javascript
if (!/^[1-9]/.test(userGuess)) {
  return alert("Solo puede ingresar numeros enteros");
}
```

Linea 72: Esta mal la sentencia del guessCount === 1, ya que esta solo permite que el usuario pueda ver el numero ingresado una sola vez, para solucionarlo se hizo que se muestre el numero que el usuario vaya ingresando, haciendo una sentencia en la cual si guessCount es mayor a cero y menor a 11, vaya actualizando mediante el usuario interactue.

Error.

```javascript
if (guessCount === 1) {
  guesses.textContent = "Número aleatorio anterior: ";
}
```

Solucion.

```javascript
if (guessCount > 0 && guessCount < 11) {
  guesses.textContent = "Número aleatorio anterior: ";
  guesses.textContent += userGuess;
}
```

Linea 77: Debemos hacer un parseo al valor del input a un numero, debido a que por defecto viene en string (esto nos ayudara para poder realizar las siguienres condicionales).

Parseo.

```javascript
userGuess = parseInt(userGuess);
```

Linea 79: El primer if esta incorrecto, ya que si el userGuess es igual al randomUser significa que el usuario gano el juego y en el original lanza el mensaje de que perdio. la solucion es modificar el if junto con el textContent a Felicitaciones! adivinaste el número! y el backgroundColor a verde.

Error.

```javascript
if (userGuess === randomNumber) {
  lastResult.textContent = "!!!Pérdistes!!!";
  lastResult.style.backgroundColor = "black";
  lowOrHi.textContent = "";
  setGameOver();
}
```

Solucion.

```javascript
if (userGuess === randomNumber) {
  lastResult.textContent = "Felicitaciones! adivinaste el número!";
  lastResult.style.backgroundColor = "green";
  setGameOver();
}
```

Linea 83: El segundo if esta incorrecto, ya que el texto a mostrar tiene que ser el de perdiste y no el de felicitaciones adivinaste el numero, la solucion es modificarlo y cambiar el texto a Perdiste!!.

Error.

```javascript
else if(guessCount === ATTEMPS) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      lastResult.style.backgroundColor = 'red';
      setGameOver();
}
```

Solucion.

```javascript
 else if (guessCount === ATTEMPS) {
      lastResult.textContent = '!!!Pérdistes!!!';
      lastResult.style.backgroundColor = 'red';
      setGameOver();
}
```

Linea 87: Reformulo todo Para poder mostrar que el numero aleatorio es mayor a el numero ingresado por el usuario y asi mismo que el numero aleatorio es menor, se crearon dos if en los cuales utilizamos operadores logicos para poder identificar si se cumple la sentencia dada.

Codigo anterior.

```javascript
else {
      lastResult.textContent = 'Incorrecto! ';
      lastResult.style.backgroundColor = 'green';
      if(userGuess < randomNumber) {
        lowOrHi.textContent = 'El número es mayor!';
      } else if(userGuess > randomNumber) {
        lowOrHi.textContent = 'El número es menor!';
      }
    }
```

Codigo modificado.

```javascript
     else if (userGuess > randomNumber) {
      lastResult.textContent = 'Incorrecto! El número es mayor!';
      lastResult.style.backgroundColor = 'black';
      lowOrHi.textContent = '';
    } else if (userGuess < randomNumber) {

      lastResult.textContent = 'Incorrecto! El número es menor!';
      lastResult.style.backgroundColor = 'black';
      lowOrHi.textContent = '';

    }
```

Linea 118: Debemos de quitar el punto antes de resulparas debido a que no estamos llamando una clase por que si se deja nos da error cuando se reinicia el juego.

Error.

```javascript
const resetParas = document.querySelectorAll(".resultParas");
```

Solucion.

```javascript
const resetParas = document.querySelectorAll("resultParas");
```
