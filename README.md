# 2020-js-vanilla-testing-000

<p align="center">
    <img src="https://github.com/GeeksHubsAcademy/2020-geekshubs-media/blob/master/image/logo.png" >	
</p>

## Temario
* [Pirámide de Pruebas](https://github.com/GeeksHubsAcademy/2020-js-vanilla-000/blob/master/README.md#pir%C3%A1mide-de-pruebas)
* [Qué se va a probar ?](https://github.com/GeeksHubsAcademy/2020-js-vanilla-000/blob/master/README.md#qu%C3%A9-se-va-a-probar)
* [Qué es un Test Unitario ?](https://github.com/GeeksHubsAcademy/2020-js-vanilla-000/blob/master/README.md#qu%C3%A9-es-un-test-unitario)
* [Cómo vamos a escribir los Test Unitarios ?](https://github.com/GeeksHubsAcademy/2020-js-vanilla-000/blob/master/README.md#c%C3%B3mo-vamos-escribir-los-test-unitarios-)
* [Qué es un convenio ?](https://github.com/GeeksHubsAcademy/2020-js-vanilla-000/blob/master/README.md#qu%C3%A9-es-un-convenio-)
* [Qué patrones vamos a usar ?](https://github.com/GeeksHubsAcademy/2020-js-vanilla-000/blob/master/README.md#qu%C3%A9-patrones-vamos-a-usar-)
* [Conclusiones](https://github.com/GeeksHubsAcademy/2020-js-vanilla-000/blob/master/README.md#conclusiones)
* [Referencias](https://github.com/GeeksHubsAcademy/2020-js-vanilla-000/blob/master/README.md#referencias)

### Pirámide de Pruebas

```
Martin Fowler escribió la pirámide de pruebas.

Los diferentes niveles de la pirámide y sus tamaños relativos representan distintos tipos de pruebas y 
cuántas se deben escribir para la aplicación. Como se puede ver, la recomendación es tener una base grande de 
pruebas unitarias, respaldada por un nivel más pequeño de pruebas de integración, con un nivel incluso 
más pequeño de pruebas funcionales.

Idealmente, cada nivel solo debería incluir las pruebas que no se puedan realizar de forma adecuada en 
un nivel inferior. Tenga presente que la pirámide de pruebas trata de decidir qué tipo de prueba necesita
para un escenario determinado.

```

<p align="center">
    <img src="https://raw.githubusercontent.com/GeeksHubsAcademy/2020-geekshubs-media/master/image/piramide-testing.png" align="center" height="255" width="300">
</p>

### Qué se va a probar?

```
Un problema común para los desarrolladores sin experiencia con la escritura de pruebas es determinar lo que 
se debe probar.

Un buen punto de partida es probar la lógica condicional.
Siempre que haya un método con un comportamiento que cambia en función de una instrucción condicional
(if-else, switch, etc.), debería poder dar idear al menos un par de pruebas que confirmen el comportamiento
correcto para determinadas condiciones. 

Si el código tiene condiciones de error, es conveniente escribir al menos una prueba para la "ruta feliz"
a través del código (sin errores) y al menos una prueba para la "ruta triste" (con errores o resultados
pocos frecuentes) para confirmar que la aplicación se comporta según lo previsto ante los errores.

Por último, hay que intentar centrarse en probar cosas en las que se pueda producir un error.

```

### Qué es un test unitario?

```
Es una forma de comprobar el correcto funcionamiento de una unidad de código.

Debemos de entender que un método solo debe de tener un solo comportamiento, pues incluir una clausula 
'if-else' nos lleva a tener dos estados. Para poder validar estos dos estados debemos de tener dos métodos
independientes que validen la clásula 'if' y otro método que valida la cláusula 'else'.

De esta manera cumpliremos el propósito de test unitario, simplemente un unidad de código.

Recuerda que para poder decir que hacemos testing, debemos de cubrir todas las salidas del método.
Piensas qué testeando solo la cláusula 'if-else' está todo hecho?
Y... si resulta que estoy comprobando el correcto funcionamiento de una división y el denominador es 0 ???

Ahí lo dejo...

```

### Cómo vamos escribir los test unitarios ?

```
Ahora mismo el alumno no debe de escribir ningún test, simplemente absorver conocimiento.

Vamos a proveerte de soluciones ya estructuradas donde aprenderas a pensar.
Para ello usaremos 'ingeniería inversa'.

Al principio te daremos la solución hecha y simplemente tendrás que analizar y absorver el conocimiento.
En una segunda iteración te daremos partes del mismo, y sabiendo que previamente obtuvistes un conocimiento
'end-to-end', deberás añadir la partes que falten.

De esta manera, iremos poco a poco afinando y puliendo la técnica del testing.

```

### Qué es un convenio ?
```
Es un acuerdo de voluntades. Dícese de ese tipo de normas que debes de tener a la hora de escribir código.

Esto permite que varios desarrolladores de diferentes partes del mundo, puedan trabajar juntos sin tener 
conflictos de sintaxis.

Al tratar una norma de escritura, todos se entienden mejor.

El uso de patrones o plantillas permite que nuestro código sea agnóstico al lenguaje del habla de cada
persona.

Piensa que tu hablas español y tu compañero que colabora en un repositorio habla chino.
Seguro que si ambos escribís en un mismo lenguaje de programación con unas normas mínimas, os entenderéis
dando igual la procedencia.

```

### Qué patrones vamos a usar ?

```
Incidiendo en la estructura de cómo vamos a definir el contenido de un método, vamos a usar un estándar.
Tu por ahora no tendras que hacer nada, simplemente absorver información.

Cuando testeemos, debemos de ser limpios y concisos.
Hay que escribir lo mínimo viable e intentar ser lo máximo expresivo posible.

Para ello vamos a usar el patrón AAA.
Dicho patrón define el cuerpo de un test en tres partes. 


* Arrange (Organizar/Inicializa) => inicializa los objetos y establece los valores de los datos 
                                    que vamos a utilizar en el Test que lo contiene.
                                    
                                    
* Act (Actuar)                   => realiza la llamada al método a probar con los parámetros preparados 
                                    para tal fin.


* Assert (Confirmar/Comprobar)   => comprueba que el método de pruebas ejecutado se comporta tal y 
                                    como teníamos previsto que lo hiciera.
                                   
Este concepto puede ser bueno a la hora de implementar pequeños métodos.
```

#### Definición de un Test normal

```js
test('Sum 1 + 2 to equal 3', function () {
  expect(sum(1, 2)).toBe(3);
});

```

#### Definición de un Test con Patrón AAA

```js
test('Sum 1 + 2 to equal 3', function () {
// Arrange
var toBe = 3;

// Act
var result = sum(1, 2);

// Assert
expect(result).toBe(toBe);
});

```

### Conclusiones
```
Después de haber leído esta pequeña introducción simplemente queremos que asientes conceptos...

La capacidad de llegar a un resultado acotando diferentes soluciones es la diferencia entre la 
persona que desarrolla y testea a la persona que testea y desarrolla.

Son dos conceptos totalmente diferente que ahora mismo no podrás apreciar.

Hay gente que tarda años en saber/ver estas diferencias... En Geekshubs queremos dejarlas claras desde 
el minuto uno de la formación. Por ello decimos que queremos que simplemente absorvas conocimiento, luego 
puliremos los detalles.

Para finalizar, te diremos que estás aprendiendo hábitos de desarrollo, capacidades de análisis y premisas 
de metolodogía ágil.

Tú aún no lo sabes, pero vas a empezar a pensar en construir tu meta poco a poco a base de pequeños Tests.  

Ahora ondea en las referencias.

```


### Referencias
  * [Martin Fowler](https://www.google.com/search?q=martin+fowler&rlz=1C1GCEU_esES890ES890&oq=martin+fowler&aqs=chrome..69i57j46j35i39l2j0l4.5068j0j4&sourceid=chrome&ie=UTF-8)
  * [Pirámide de Pruebas - microsoft](https://docs.microsoft.com/es-es/dotnet/architecture/modern-web-apps-azure/test-asp-net-core-mvc-apps)
  * [Prueba unitaria - wikipedia](https://es.wikipedia.org/wiki/Prueba_unitaria)
  * [Unit-Testing](https://less.works/less/technical-excellence/unit-testing.html)
  * [Patrón AAA](https://uniwebsidad.com/libros/tdd/capitulo-5/las-tres-partes-del-test-aaa)
  
  
  
  <div>
    <p align="center">
        <img src="https://github.com/GeeksHubsAcademy/2020-geekshubs-media/blob/master/image/pixel.png" >	
    </p>
  </div>
  
  <footer>
     <div>
        <a href="https://github.com/GeeksHubsAcademy/2020-js-vanilla-testing-FFFF"><< Atrás</a>
         <a href="https://github.com/GeeksHubsAcademy/2020-js-vanilla-testing-000/blob/master/README.md#referencias">
        <img src="https://github.com/GeeksHubsAcademy/2020-geekshubs-media/blob/master/image/pixel.png" align="center"                  height="10" width="714"/>
         </a>
         <a href="https://github.com/GeeksHubsAcademy/2020-js-vanilla-testing-000">Siguiente >></a>   
    </div>
 </footer>



