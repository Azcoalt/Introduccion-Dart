# Introduccion a dart 

![Dart](https://img.shields.io/badge/dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white)

**Indice**
1. [Inicio](#inicio)
2. [Tipos de datos y variables](#tipos-de-datos-y-variables)
3. [Tipo  de dato lista](#tipo-de-dato-lista)
4. [Tipo de dato mapa](#tipo-de-dato-mapa)
5. [Funciones](#funciones)
6. [Clases](#clases)
7. [Clases abstractas](#clases-abstractas)
8. [Extends](#extends)
9. [Mixins](#mixins)
10. [Futures](#futures)
11. [Async-Await](#async-await)

## Inicio
Para poder empezar a programar en dart se deve tener en consideracion que es similar a java
por lotanto siempre va a ver una clase main que es en donde se 
ejecutara el codigo que nosostros escribamos 

El siguiente ejemplo es con un hola mundo 

```dart
void main(){
  print('hola mundo');
}
```

El void es que no retorna nada 

## Tipos de datos y variables

Para poder declarar varibles se asemeja un poco a javascript 

se inicializa la varible y se le da un valor como en ele siguinte ejemplo.

```dart
void main(){
  
  //Strings
  //variables
  var nombre = 'Tony';
  var apellido = 'stark';
}
```

para poder concatenar los strings o cualquier otro tipo de variable se usa el signo de $ para que pudad concatenarse

ejemplo:
```dart
void main(){
  
  //Strings
  //variables
  var nombre = 'Tony';
  var apellido = 'stark';

    //concatenacion e imprecion de las variables
  print('$nombre $apellido');
}
```
Nota: No se recominda usar var ya que al ser un lenguaje de programacion de tipado fuerte serecomienda mas usar el tipo de la variable como en java String, int, double, etc.

otro tipo de decalcion es con final este es como si fuera const en javascript, esto hace que el valor de la variable no cambie 

ejemplo:

```dart
void main(){
  
  //Strings
  //variables
  final nombre = 'Tony';//no cambia su valor
  String apellido = 'stark';

    //concatenacion e imprecion de las variables
  print('$nombre $apellido');
}
```

con numeros ejemplo:

```dart
void main(){ 
  //numeros 
  int empleados = 10;
  double salario = 1893.54;
  
  print(empleados);
  print(salario);
  print('$empleados $salario');
}
```

tipo boleano ejemplo:

```dart
void main(){
  //boleano
  
  bool isActive = true;
  
  if (isActive){
    print('Esta activo');
  }else{
    print('No esta activo');
  }
}
```

para podertener una variable el valor null es nesesario unas modificaciones

```dart
void main(){
  //boleano
  bool? isActive;
  
  if (isActive == null){
    print('isActive es null');
  }else{
    print('No es null');
  }
}
```

## Tipo de dato lista

En dar se le conose mas como listas en ves de areglos en el sguiente ejemplo se ve como se inicializa una lista

```dart
void main(){
    //lista
  List numeros = [1,2,3,4,5,6,7,8,9,10];
  
  print(numeros);
}
```

el metodo add() agraga un elemeto a la lista

```dart
void main(){
    //lista
  List numeros = [1,2,3,4,5,6,7,8,9,10];
  
  numeros.add(11);
  print(numeros);
}
```

y para buscar un elemeto se hace como en otros lenguajes se busca en posison en base 0

```dart
void main(){
    //lista
  List numeros = [1,2,3,4,5,6,7,8,9,10];//manra generica
  
  print(numeros[0]);
}
```
para definir una lista se hace de la siguiente menera

```dart
void main(){
    //lista
  List<int> numeros = [1,2,3,4,5,6,7,8,9,10];//la lista va a ser de tipo entero(int)
  numeros.add(11);
  print(numeros);
}
```

## Tipo de dato mapa

El tipop de dato mapa en dart son los diccionarios en otros lenguajes ejemplo

```dart
void main(){
  //mapa
  Map persona = {
    'nombre':'juna',
    'edad': 32,
    'estado': 'soltero'
  };
  
  print(persona);
}
```

para poder acceder a un elemento se hace igual como anterior mente

```dart
void main(){
  //mapa
  Map persona = {
    'nombre':'juna',
    'edad': 32,
    'estado': 'soltero'
  };
  
  print(persona['nombre']);//accede al nombre
}
```

tambien lo recomendable es definir el mapa como en las listas ejemplo
```dart
void main(){
  //mapa
  Map<String, dynamic> persona = {
    'nombre':'juna',
    'edad': 32,
    'estado': 'soltero'
  };
  //dynamic es dinamico acepta cualquier dato
  
  print(persona);
}
```

## Funciones 

Para una fuuncion se maneja similar como enotros lenguajes de programacion

```dart
void main(){
  saludar();
}
//nueva funcion
void saludar(){
  print('hola mundo')
}
```

void es para retornar cualquier cosa eso quiere decir que es de tipo dynamic tambien se puede usar sin el void

para poder pasarle un argumento setien que declarar en la segunda funcion para poder pasar un argumento

ejemplo:
```dart
void main(){
  final nombre = 'fernando';
  saludar(nombre);
}

void saludar(String n){
  print('hola $n');
}
```
para poder utilizar los argumentos que nesesitan afurza un tipo de dato se hace de la sguiente manera 

```dart
void main(){
  final nombre = 'fernando';
  saludar();
}

void saludar([String n = 'no name']){
  print('hola $n');
}
```

tambien se puden usar dos un opcional y un obligatorio
```dart
void main(){
  final nombre = 'fernando';
  saludar(nombre, 'hola');
}

void saludar(String nombre, [String mensaje = 'Hi']){
  print('$mensaje $nombre');
}
```

para usar la funciones de manera de que siempre requieren los argumentos es nesesario utilizar el required

ejemplo:

```dart
void main(){
  final nombre = 'fernando';
  saludar(nombre, 'hola');
  saludar2(mensaje: 'hi', nombre: nombre);
}

void saludar(String nombre, [String mensaje = 'Hi']){
  print('$mensaje $nombre');
}

void saludar2({required String nombre, required String mensaje}){
  print('$mensaje $nombre');
}
}
```

## Clases 

Para las clases se usa de la siguiente manera
```dart
void main(){
  final wolverine = new Heroe();//inicializas la clase
}

class Heroe{
  
}
```

metodos para acceder a los valores que se le quiera poner
```dart
void main(){
  final wolverine = Heroe();
  wolverine.nombre = 'Logan';//se leponen valores
  wolverine.poder = 'regeneracion';
  
  print(wolverine);
}

class Heroe{
  String? nombre;
  String? poder;
  
  //accede a los valores del string
  @override
  String toString(){
    return 'Heroe: nombre: ${this.nombre}, poder: ${this.poder}';//regesa el valor
  }
}
```

la mejor practica es que se haga mediante un con cosntructor inicializando las variable

ejemplo:
```dart
void main(){
  final wolverine = Heroe(nombre:'logan', poder:'regeneracion');
  
  print(wolverine);
}

class Heroe{
  String? nombre;
  String? poder;
  
  //constructor
  Heroe({required this.nombre, required this.poder});
  
  //accede a los valores del string
  @override//opcional
  String toString(){
    return 'Heroe: nombre: ${this.nombre}, poder: ${this.poder}';//regesa el valor
  }
}
```

Los constructores con nombres son similares a las peticiones http si que se nesecita un constructor 

Ejemplo: primera forma se nesecita que lasvariables puedan resivir null 
```dart
void main(){
  final rawjson = {
    'nombre': 'tony',
    'poder': 'dinero'
  };
  
  final ironman = Heroe.fromJson(rawjson);
  print(ironman);
}

class Heroe{
  String? nombre;
  String? poder;
  
  //constructor
  Heroe({required this.nombre, required this.poder});
  
  //constructor de nombre 
  Heroe.fromJson(Map<String,String> json){
    this.nombre = json['nombre']!;
    this.poder = json['poder']!;
  }
  
  //accede a los valores del string
  @override
  String toString(){
    return 'Heroe: nombre: ${this.nombre}, poder: ${this.poder}';//regesa el valor
  }
}
```

Ejemplo: recomendable ya que nuestras variables estan para obtener siempre un valor

```dart
void main(){
  final rawjson = {
    'nombre': 'tony',
    'poder': 'dinero'
  };
  
  final ironman = Heroe.fromJson(rawjson);
  print(ironman);
}

class Heroe{
  String nombre;
  String poder;
  
  //constructor
  Heroe({required this.nombre, required this.poder});
  
  //constructor de nombre 
  Heroe.fromJson(Map<String,String> json):
    this.nombre = json['nombre']!,
    this.poder = json['poder'] ?? 'No tiene poder';
  
  
  //accede a los valores del string
  @override
  String toString(){
    return 'Heroe: nombre: ${this.nombre}, poder: ${this.poder}';//regesa el valor
  }
}
```

para los get y set se ven similares como otros lenguajes

Ejemplo:
```dart
import 'dart:math' as math;

void main(){
 final cuadrado = Cuadrado(5);
  
  cuadrado.area = 100;//asigna
  
  print('lado: ${cuadrado.lado}');
  print('area get: ${cuadrado.area}');
}

class Cuadrado{
  double lado;
  
  double get area {
    return this.lado * this.lado;
  }
  
  set area(double valor){
    this.lado = math.sqrt(valor);//raiz cuadrada
  }
  
  Cuadrado(double lado):
  this.lado = lado;
}
```

## Clases Abstractas

Una clse abstracta es una clase que puedan otras clases puedan implementar lo que tiene esa clase 

Ejemplo:
```dart
void main(){
  final perro = Animal();//esto no es permitido
}

//clase abstracta 
abstract class Animal{
  int? patas;
  
  Animal();
  
  void emitirSonido();
}
```

Ejemplo mas practico y mejor:
```dart
void main(){
  final perro = Perro();//esto es permitido
  
  perro.emitirSonido();
}

//clase abstracta 
abstract class Animal{
  int? patas;
  
  void emitirSonido(){}
}

class Perro implements Animal{
  @override
  int? patas;
  @override
  void emitirSonido(){
    print('Guauuuuuuu');
  }
}
```

un poco mas complejo:
```dart
void main(){
  final perro = Perro();//esto no es permitido
  
  //perro.emitirSonido();
  sonidoAnimal(perro);
}

void sonidoAnimal(Animal animal){
  animal.emitirSonido();
}

//clase abstracta 
abstract class Animal{
  int? patas;
  
  void emitirSonido(){}
}

class Perro implements Animal{
  @override
  int? patas;
  @override
  void emitirSonido(){
    print('Guauuuuuuu');//funcion flecha
  }
}
```

con mas clses que implementa la clase adstracta
```dart
void main(){
  final perro = Perro();//esto no es permitido
  final gato = Gato();
  
  //perro.emitirSonido();
  sonidoAnimal(perro);
  sonidoAnimal(gato);
}

void sonidoAnimal(Animal animal){
  animal.emitirSonido();
}

//clase abstracta 
abstract class Animal{
  int? patas;
  
  void emitirSonido(){}
}

class Perro implements Animal{
  @override
  int? patas;
  @override
  void emitirSonido(){
    print('Guauuuuuuu');
  }
}

class Gato implements Animal{
  @override
  int? patas;
  int? cola;
  
  @override
  void emitirSonido(){
    print('Miauuuu');
  }
}
```

## Extends
Extends es una palabra reservada para extender la funcionalidad de una clase tambien se puede usar classes abstractas

lo que hace es extender la funcionalidad en una clase
```dart
void main(){
 final superman = Heroe('superman');
 
  print(superman);
}

abstract class Personaje{
  String? poder;
  String nombre;
  
  Personaje(this.nombre);//constructor
  
  @override
  String toString(){
    return '$nombre - $poder';
  }
}

class Heroe extends Personaje{
  Heroe(String nombre):super(nombre);//agara el constructor
}
```

## Mixins

Los mixis son como caracteristicas especiales que pueden usar las otras clases 

para mas informacion consulta <a href='https://medium.com/flutter-community/dart-what-are-mixins-3a72344011f3'>mas</a>

en pocas palabras es como si metieras cajas dentro de otras cajas pero que tienen que cumplir cirtas caracterictrica

usamos este ejemplo:
```dart
abstract class Animal{}

abstract class Mamifero extends Animal{}
abstract class Ave extends Animal{}
abstract class Pez extends Animal{}

//caracteristica 
abstract class Volador{
  void volar(){
    print ('Estoy volando');
  }
}
abstract class Caminante{
  void caminar(){
    print ('Estoy caminando');
  }
}
abstract class Nadador{
  void nadar(){
    print ('Estoy nadando');
  }
}


//objetos con invocacion a sus caracteristicas
//mamiferos
class Delfin extends Mamifero with Nadador{}
class Murcielago extends Mamifero with Caminante, Volador{}
class Gato extends Mamifero with Caminante{}

//volador
class Paloma extends Ave with Volador, Caminante{}
class Pato extends Ave with Volador, Caminante, Nadador{}

//nadador
class Tiburon extends Pez with Nadador{}
class PezVolador extends Pez with Nadador, Volador{}
void main(){
  //delfin
  final delfil = Delfin();
  print('Delfin:');
  delfil.nadar();
  
  //murcielago
  final dracula = Murcielago();
  print('Murcielago:');
  dracula.caminar();
  dracula.volar();
  
  //gato
  final donGato = Gato();
  print('Gato:');
  donGato.caminar();
  
  //paloma
  final dove = Paloma();
  print('Paloma:');
  dove.caminar();
  dove.volar();
  
  //pato
  final duck = Pato();
  print('Pato:');
  duck.caminar();
  duck.nadar();
  duck.volar();
  
  //tiburon
  final shark = Tiburon();
  print('Tiburon:');
  shark.nadar();
  
  //pez volador
  final flyingFish = PezVolador();
  print('Pez Volador:');
  flyingFish.nadar();
  flyingFish.volar();
  
}
```

## Futures

Como en java script es una promesa que es algo que se va a ejecutar a diferente tiempo

Ejemplo:
```dart
void main(){
  print('Antes de la peticion');
  
  httpGet('https://google.com/welcom').then((data){
    print(data);
  });
  
  print('Fin del programa');
}

Future httpGet(String url){
  return Future.delayed(Duration(seconds:3), () {
    return 'Hola mundo - 3 segundos';
  });
}
```

## Async-Await

Es siilar que el future solo que este regresa la funcion y tiene tener siertas modificaciones

Ejemplo:
```dart
void main()async{
  print('Antes de la peticion');//ejecuta primero
  
  print(await httpGet('https://google.com/welcom'));//espera
  
  final nombre = await getNombre('10');//final el resto
  print(nombre);
  
  print('Fin del programa');
}

Future<String> getNombre(String id) async{
  return 'id: $id-Fernando';
}

Future httpGet(String url){
  return Future.delayed(Duration(seconds:3), () {
    return 'Hola mundo - 3 segundos';
  });
}
```
El await solo funciona en funciones acincronas con el async como se muentra en el void