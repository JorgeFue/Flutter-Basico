# pruebas

# Curso-basico-FLutter
Básico sobre flutter

## Hola mundo

  En este apartado podre observar como hacer un hola mundo en visual code con flutter.

> Flutter: es un lenguaje multiplataforma

    
###1.- Primero es mandar llamar la raiz donde se llamaran los widgets que cubriran el 100% del espacio en el celular.
 ```sh
    void main() => runApp(Aqui_va_el_widget_raiz);
```
con los widgets se trabaja sobre sus propiedades en su constructor .

###2.- Se intancia un objeto de tipo widget, en este caso sera un objeto de tipo center()

```sh
    void main() => runApp( center ( Prop_del_contructor ) );
```
para ver las propiedades del constructor de los widgets se visualizan utilizando la combinacion de teclas: "Ctrl + Espacio"

En este este caso utilizaremos la propiedad Clild, como su nombre lo dice es un hijo y solo se le podra agregar un hijo.

```sh
    void main() => runApp( 
        Center (
            child: "aqui_va_el_widget_siguiente",
        ),//center
    );//runApp
```
Despues dentro del child se agrega el widget Text: aqui se pondra las frases necesarias o el texto que se quiera mostrar

```sh
    void main() => runApp( 
        Center (
            child: Text(
              'Hello World',
              textDirection: TextDirection.ltr,
            ),//center
    );//runApp
```
y liisto el hola mundo esta listo.

## 2.- App que genere una lista de nombres aleatorios.

 Primero nuestra funcion main.
 ```sh
 void main() => runApp( MyApp() );
 ```
 Aqui crearemos nuestro propio widget que heredara de StatelessWidget (Son widgets sin estado), todo widget tiene un medo will entonces tiene que llevar un override que retorna un widget.
 
 ```sh
 void main() => runApp( MyApp() );

class MyApp extends StatelessWidget {
  
  @override
  Widget build(BuildContext context) {
    return null;
  }

}
```

en el return lo que se retornara un MaterialApp ya que en este widget trae muchos materiales para trabajar y crear nuestro widget. 

```sh
void main() => runApp( MyApp() );

class MyApp extends StatelessWidget {
  
  @override
  Widget build(BuildContext context) {
    
    return MaterialApp( "Sobre_las_prop_del_ constructor_se_trabaja" );
  }

}
```

Dentro del MaterialApp se comenzara a crear nuestro widget 

```sh
void main() => runApp( MyApp() );

class MyApp extends StatelessWidget {
  
  @override
  Widget build(BuildContext context) {
    
    return MaterialApp(  
    title: 'Bienvenido a Flutter',
    );//MaterialApp
    
  }//widget Build

}//class MyApp
```

Dentr de las propiedades esta el title: "Aui_se_pone_el_encabezado",

```sh
void main() => runApp( MyApp() );

class MyApp extends StatelessWidget {
  
  @override
  Widget build(BuildContext context) {
    
    return MaterialApp(  
    
    title: 'Bienvenido a Flutter',
    
    home: 
    );//MaterialApp
    
  }//widget Build

}//class MyApp
```
despues se pone la propiedad home que es donde iran los widget que costruiran el widget

```sh
void main() => runApp( MyApp() );

class MyApp extends StatelessWidget {
  
  @override
  Widget build(BuildContext context) {
    
    return MaterialApp(  
    
        title: 'Bienvenido a Flutter',
    
        home: Scaffold(
            
        );//Scaffold
    );//MaterialApp
  }//widget Build
}//class MyApp
```
Se agrego un widget llamado Scaffold es un widget especial que sirve como una aplicacion prediseñada en su contructor se tienen varios elemtos que ayudaran a complementar el widget deseado

```sh
void main() => runApp( MyApp() );

class MyApp extends StatelessWidget {
  
  @override
  Widget build(BuildContext context) {
    
    return MaterialApp(  
    
        title: 'Bienvenido a Flutter',
    
        home: Scaffold(
            
            appBar: AppBar(
                title: Text('Bienvenido a Flutter'),
            ),//AppBar
        );//Scaffold
    );//MaterialApp
  }//widget Build
}//class MyApp
```
Se pone la propiedad appBar para colocar ahi el widget AppBar(),y para que se valla construllendo la app apilaremos widget sobre widget, ponemos tile: y le cargamos el Text('escribe loq ue quieras que muestre la app de titulo').

```sh
void main() => runApp( MyApp() );

class MyApp extends StatelessWidget {
  
  @override
  Widget build(BuildContext context) {
    
    return MaterialApp(  
    
        title: 'Bienvenido a Flutter',
    
        home: Scaffold(
            
            appBar: AppBar(
                title: Text('Bienvenido a Flutter'),
            ),//AppBar
            
            body: Center(
                child: Text('Hola Mundo'),
            ),//Center 
            
        );//Scaffold
    );//MaterialApp
  }//widget Build
}//class MyApp
```
se agrega la propiedad body: esta es el cuepo del lienzo.
Le agrgaremos un widget "center()" y en su propiedad se pone un "child:" dentro de el se coloca otro widget, en este caso se colocara texto para recrear un hola mundo.
------------------------------------------------------------------------------------

#Importar una paqueteria que genera palabras

comenzamos siguiendo los pasos de la pagina: https://pub.dev/packages/english_words#-installing-tab-

despues importamos el package.

```sh
import 'package:flutter/material.dart';
import 'package:english_words/english_words.dart';

void main() => runApp( MyApp() );

class MyApp extends StatelessWidget {
  
  @override
  Widget build(BuildContext context) {
    
    return MaterialApp(  
    
        title: 'Bienvenido a Flutter',
    
        home: Scaffold(
            
            appBar: AppBar(
                title: Text('Bienvenido a Flutter'),
            ),//AppBar
            
            body: Center(
                child: Text('Hola Mundo'),
            ),//Center 
            
        );//Scaffold
    );//MaterialApp
  }//widget Build
}//class MyApp
```
en seguida instanciamos una constante llamada "Final" es para que se sepa al momento de ejcutarla,

```sh
import 'package:flutter/material.dart';
import 'package:english_words/english_words.dart';

void main() => runApp( MyApp() );

class MyApp extends StatelessWidget {

    final wordPair = WordPair.random();
  
  @override
  Widget build(BuildContext context) {
    
    return MaterialApp(  
    
        title: 'Bienvenido a Flutter',
    
        home: Scaffold(
            
            appBar: AppBar(
                title: Text('Bienvenido a Flutter'),
            ),//AppBar
            
            body: Center(
                child: Text(wordPair.asPascalCase),
            ),//Center 
            
        );//Scaffold
    );//MaterialApp
  }//widget Build
}//class MyApp
```
se intancea el final y se crea la variable ramdom de palabras, se manda llamar en el text del body
