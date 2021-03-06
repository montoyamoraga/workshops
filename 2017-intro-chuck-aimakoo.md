# 2017_10_intro_chuck_aimakoo.md


## Sobre el taller

Este taller fue dictado por Aarón Montoya-Moraga en el Centro Cultural España, Santiago de Chile, en el marco del festival Aimakoo, miércoles 11 de octubre 2017.

## Asistentes

Un minuto por persona, quiénes son, cuánto saben de sonido y de programación

## Instrucciones

Instalar ChucK: ir a  [http://chuck.cs.princeton.edu/](http://chuck.cs.princeton.edu/) y a download ChucK.

## Primer programa

```chuck
<<< "Hello World" >>>;
```

## Primer oscilador

```chuck
//Conecta una onda sinusoidal
SinOsc s => dac;
//Define la ganancia del oscilador como 0.6
0.6 => s.gain;
//Define la frecuencia del oscilador como 220
220 => s.freq;
//Permite que toque por un segundo
second => now;
```

## Varias notas musicales

```chuck
//Bloque 1
/* Música con onda sinusoidal
por un programador de ChucK
Enero 2025
*/

//Bloque 2
//Conecta una onda sinusoidal al dac
SinOsc s => dac;

//Bloque 3
//Toca una nota
//Define la ganancia como 1.0 y la frecuencia como 220 Hz.
//Deja que se ejecute por 0.3 segundos haciendo ChucKing a now.
220 => s.freq;
1.0 => s.gain;
0.3 :: second => now;

//Bloque 4
//Calla tu oscilador por 0.3 segundos para separarlo de la siguiente nota
0.0 => s.gain;
0.3 :: second => now;

//Bloque 5
//Toca una nota, con la misma altura
//Repite el proceso de los bloques 1 y 2
1.0 => s.gain;
0.3 :: second => now;

0.0 => s.gain;
0.3 :: second => now;

//Bloque 6
//Toca dos notas adicionales, más altas, menor volumen
//Repite el mismo patrón de los bloques 1, 3 y 4
//pero con una diferente frecuencia y volumen
330 => s.freq;
0.3 => s.gain;
0.3 :: second => now;

0.0 => s.gain;
0.3 :: second => now;

0.3 => s.gain;
0.3 :: second => now;

0.0 => s.gain;
0.3 :: second => now;
```

## Bucles

```chuck
Impulse imp => ResonZ filt => NRev rev => dac;
0.04 => rev.mix;
100.0 => filt.Q => filt.gain;

while (1) {
  Std.mtof(Math.random2(60,84)) => filt.freq;
  1.0 => imp.next;
  100 :: ms => now;
}
```

## Variables

```chuck
//declara un entero
int myPitch;

//almacena una variable
220 => myPitch;

//imprime su valor
<<< myPitch >>>;
```

## Duraciones

```chuck
4 :: quarter => dur whole;

4 * quarter => dur whole;

whole / 2 => dur half;

quarter /2 => dur eighth;
```

## MIDI

```chuck
<<< Std.mtof(64) >>>;
```

```chuck
//cadena de sonido
TriOsc t => dac;
0.4 => t.gain;

//bucle
for (0 => int i; i < 127; i++) {
  //(1) Usar Std.mtof para convertir de número de nota a frecuencia
  Std.mtof(i) => float Hz;
  //imprimir el resultado
  <<< i, Hz >>>
  //(2) Definir en Hz la frecuencia del oscilador
  Hz => t.freq;
  //Hacer avanzar el tiempo
  200 :: ms => now;
}
```

## Conversión

| Método           | Resultado | Descripción                       |
| :--------------  | :-------- | :-------------------------------- |
| Std.atoi(string) | int       | Convierte ASCII (string) en int   |
| Std.atof(string) | float     | Convierte ASCII (string) en float |
| Std.itoa(int)    | string    | Convierte int en ASCII (string)   |
| Std.ftoa(float)  | string    | Convierte float en ASCII (string) |

## Aleatoreidad

| Método                               | Resultado | Descripción |
| :----------------------------------  | :-------- | :---------- |
| Math.random()                        | int       | Genera enteros aleatorios entre 0 y Math.RAMDOM_MAx   |
| Math.random2(int min, int max)       | int       | Genera enteros aleatorios en el rango [min, max]|
| Math.randomf()                       | float     | Genera números de punto flotante en el rango [0, 1] |
| Math.random2f(float min, float max)  | float     | Genera números de punto flotante en el rango [min, max] |

```chuck
//Música aleatoria de onda cuadrada
SqrOsc s => dac;

//(1)El bucle for toca 16 notas
for (0 => int i; i < 16; i++) {
  //(2) Nota entera aleatoria (C3 - C5)
  Math.random2(48, 72) => int myNote;
  //(3) Ganancia aleatoria entre .05 y .9
  Math.random2f(0.05, 0.9) => float myGain;
  //(4) Imprime la nota y la ganancia actuales
  <<< myNote, myGain>>>;
  //(5) Define la frecuencia y la ganancia del oscilador
  Std.mtof(myNote) => s.freq;
  myGain => s.gain;
  //(6) Deja que cada note suene durante 1/5 de segundo
  0.2 :: second => now;
}
```

## Arreglos

```chuck
[57, 57, 64, 64, 66, 66, 64] @=> int a[];

<<< a[0], a[1], a[2], a[3], a[4], a[5], a[6] >>>
```

```chuck
//Declara e inicializa un arreglo
[57, 57, 64, 64, 66, 66, 64] @=> int a[];

//lectura del arreglo según índice
//(1) busca la nota en el arreglo según un índice entero
a[2] => int myNote;

//(2) lo imprime
<<< myNote >>>;

//¿quieres modificar los datos? ¡cero problema! (imprime también)
//(3) cambia el valor elemento del arreglo según índice
61 => a[2];
<<< myNote, a[2] >>>;

<<< a[0], a[1], a[2], a[3], a[4], a[5], a[6] >>>
```

```chuck
//usemos un oscilador de onda cuadrada
//(1) oscilador de onda cuadrada para la melodía
SqrOsc s => dac;

//ganancias para separar nuestras notas
//(2) ganancias de notas encendidas y apgadas
0.7 => float onGain;
0.0 => float offGain;

//declarar e inicailzar un arreglo de notas MIDI
//(3) arreglo de notas MIDI para la melodía
[57, 57, 64, 64, 66, 66, 64, 62, 62, 61, 61, 59, 59, 57] @=> int a[];

//bucle que recorre cada element del arreglo
for (0 => int i; i < a.cap(); i++) {
  //(4) imprime el índice y la nota del arreglo
  <<< i, a[i] >>>;

  //define la frecuencia y la ganancia para prender tu nota
  //(5) define la altura de las notas de melodía
  Std.mtof(a[i]) => s.freq;
  //(6) encendido de la nota
  onGain => s.gain;
  //duración de la nota encendida
  0.3 :: second => now;;

  //apaga tu nota para separarla de la siguiente
  //(8) nota apagada
  offGain => s.gain;
  0.2 :: second => now;
}
```

## Lectura de archivos

```chuck
//Uso de SndBuf para reproducir un archivo de sonido
//por programador de ChucK, diciembre 2050
SndBuf mySound => dac;

//obtener la direccion del directorio
//(1) obtiene el directorio actual de trabajo
me.dir() => string path;
//archivo de sonido que queremos reproducir
"/audio/snare_01.wav" => string filename;

// signo + concatena strings
//(2) construye una direccion completa del archivo de sonido
path + filename => filename;

//indicarle a SndBuf que lea este archivo
//(3) hacer ChucKing de un string al metodo .read de SndBuf causa que cargue ese archivo
filename => mySound.read;

//definir la ganancia
0.5 => mySound.gain;

//reproducir el sonido desde el princpio
//hacer ChucKing de un numero al metodo .pos (de posicion) de un SndBuf causa que empiece a reproducirse desde esta posicion en el arreglo (en este caso, desde el principio)
0 => mySound.pos;

//hacer que el tiempo transcurra para poder escuchar el sonido
second => now;
```

## Reproducción en reversa

```chuck
//Reproducción de sonidos en reversa
//por programador de ChucK, 4102 oiluj
//La fecha está al revés, tal como el sonido dentro de poco
SndBuf mySound => dac;

//(1) Construye la dirección del archivo y para cargar en SndBuf
me.dir() + "/audio/hihat_04.wav" => mySound.read;

//(2) Averigua cuán largo es el sonido (en número de samples)
mySound.samples() => int numSamples;

//reproduce una vez el sonido hacia adelante
0 => mySound.pos;
//(3) deja que el sonido sea reproducido
numSamples :: samp => now;

//y una vez hacia atrás
//(4) Hace que la posición del buffer sea el final del archivo
numSamples => mySound.pos;
//(5) Hace que la reproducción sea en reversa
-1.0 => mysound.rate;
// Reproduce el archivo completo, pero en reversa
numSamples :: samp => now;
```

## Mútiples samples

```chuck
//Reproduce múltiples sonidos
//por programador de ChucK, julio 2023
SndBuf snare => dac;

//construye y puebla un arreglo de direcciones de archivos de sonido + nombres
//(1) Crea y puebla un arreglo de nombres de archivos de sonido
string snare_samples[3];
me.dir() + "/audio/snare_01.wav" => snare_samples[0];
me.dir() + "/audio/snare_02.wav" => snare_samples[1];
me.dir() + "/audio/snare_03.wav" => snare_samples[2];

//bulce infinito
while (true)
{
  //escoge un número aleatorio entre 0 y el número de archivos - 1
  //(2) Escoge un número aleatorio entre 0 y 2
  Math.random2(0, snare_samples.cap() - 1) => int which;

  //carga ese archivo
  //(3) Carga el archivo aleatorio asociado
  snare_samples[which] => snare.read;

  //Deja que el tiempo transcurra para la reproducción
  0.5 :: second => now;
}
```

## Máquina de ritmos

```chuck
//Máquina de ritmos, versión 1.0
// por programador con ritmo, 31 de diciembre 1999

//SndBufs para bombo (kick, bass drum) y caja (snare)
//(1) SndBuf a mezclador Gain master y a dac
SndBuf kick => Gain master => dac;
//(2) Otro sndBuf al mezclador Gain master
SndBuf snare => master;

//carga algunos archivos
//(3) Carga tus archivos de sonido
me.dir() + "/audio/kick_01.wav" => kick.read;
me.dir() + "/audio/snare_01.wav" => snare.read;

while(true)
{
  //En el tiempo 1, toca solo el bombo
  //(4) En los tiempos impares, solo toca el bombo
  0 => kick.pos;
  0.6 :: second => now;

  //Toca ambos tambores en el tiempo 2
  //(5) En cada tiempo par, toca tanto el bombo como la caja
  0 => kick.pos;
  0 => snare.pos;
  0.6 :: second => now;
}
```

## Grabar

Abrir terminal en Mac o cmd en Windows, hacer cd a la carpeta workshops-master

```shell
cd Desktop
cd workshops-master
```
Ejecutar con chuck el archivo a sonar seguido de rec-auto.ck

```shell
chuck example.ck rec-auto.ck
```

y queda un archivo wav, yay! =)
