[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/EID3BRwM)

# Unidad 1

## 1. CPU
[Central processing unit](https://en.wikipedia.org/wiki/Central_processing_unit)

is the most important processor in a given computer.Its electronic circuitry executes instructions of a computer program, such as arithmetic, logic, controlling, and input/output (I/O) operations.

[What is a central processing unit (CPU)?](https://www.ibm.com/think/topics/central-processing-unit)

central processing unit (CPU) is the primary functional component of a computer. The CPU is an assemblage of electronic circuitry that run a computer’s operating system and apps and manage a variety of other computer operations. A CPU is, essentially, the active brain of the computer. The CPU is the invisible manager inside the computer where data input is transformed into information output. It stores and executes program instructions through its vast networks of circuitry.

## 2. ALU
[What are the components in a CPU?](https://www.ibm.com/think/topics/central-processing-unit)

The arithmetic/logic unit (ALU) handles all arithmetic operations and logical operations. Its math functionality is based on four types of operations (addition, subtraction, multiplication and division). Logical operations typically involve some type of comparison (such as of letters, numbers or special characters) that’s tied to a particular computer action.

## 3. Registros
[Registros: tomado de chatGPT](https://chatgpt.com/)

Los registros son elementos de almacenamiento de datos dentro de un procesador o una unidad de procesamiento central (CPU). Pueden clasificarse en dos categorías principales:

Registros de propósito general:

Estos registros se utilizan para almacenar datos temporales y resultados de operaciones dentro del CPU. Son accesibles para el programa en ejecución y se utilizan para una variedad de propósitos, como almacenar operandos para operaciones aritméticas y lógicas, guardar resultados intermedios, y realizar transferencias de datos entre diferentes partes del sistema.

Registros específicos:
Este grupo incluye registros que desempeñan funciones específicas y críticas dentro del funcionamiento del procesador. Algunos ejemplos comunes son:

* Program Counter (PC): Es un registro que contiene la dirección de la siguiente instrucción a ejecutar por la CPU. Indica la posición en la memoria de la siguiente instrucción a ejecutar secuencialmente.

* Stack Pointer (SP): Este registro apunta al tope de la pila en la memoria. La pila se utiliza para gestionar datos temporalmente, como la información de retorno de funciones y variables locales.

* Registro de Estado (o Flags): Contiene bits que indican el estado actual de la CPU después de la ejecución de una operación. Por ejemplo, puede indicar si una operación resultó en un valor cero, negativo o si hubo un desbordamiento.

* Registro de Datos (o Accumulator): En algunos diseños de CPU, el registro de datos principal o acumulador se utiliza para operaciones aritméticas y lógicas específicas.

Estos registros específicos son esenciales para el control del flujo de ejecución, la gestión de datos y la ejecución de instrucciones dentro de la CPU, asegurando que las operaciones se realicen de manera eficiente y ordenada.

## 4. Unidad de control 
[Guiding concepts: Data storage and memory](https://www.ibm.com/think/topics/central-processing-unit)

The control unit of the CPU houses circuitry that guides the computer system through a system of electrical pulses and notifies it to execute high-level computer instructions. But despite its name, the control unit itself doesn’t control individual apps or programs; instead, it assigns those tasks as a human manager assigns particular jobs to different workers.

## 5. Buses de datos y de dirección 

[Bus de Datos y de Dirección: tomado de chatGPT](https://chatgpt.com/)

En computación, especialmente en el contexto de los sistemas de hardware y arquitectura de computadoras, los buses de datos y de dirección son componentes fundamentales que facilitan la comunicación y el intercambio de información entre diferentes partes del sistema.

Bus de Datos: 

El bus de datos es un conjunto de cables o líneas que permiten la transferencia de datos entre diversos componentes de un sistema informático. Estos componentes pueden incluir la CPU, la memoria RAM, dispositivos de entrada/salida (como discos duros, tarjetas gráficas, etc.), y otros dispositivos periféricos.
La función principal del bus de datos es transportar información binaria (bits) que representan datos entre los diferentes componentes del sistema. Por ejemplo, cuando la CPU necesita leer o escribir datos en la memoria RAM, utiliza el bus de datos para transmitir la información.
La anchura del bus de datos (medida en bits) determina la cantidad de datos que se pueden transferir simultáneamente. Por ejemplo, un bus de datos de 64 bits puede transferir 64 bits de datos en una sola operación.

Bus de Dirección:

El bus de dirección es otro conjunto de cables o líneas que se utilizan para especificar la dirección física de la memoria o de los dispositivos periféricos a los que se desea acceder desde la CPU.
A diferencia del bus de datos que transfiere los datos en sí, el bus de dirección transfiere direcciones (números binarios) que indican la ubicación específica de memoria o de dispositivos periféricos.
La cantidad de líneas del bus de dirección determina la cantidad de direcciones únicas que se pueden especificar. Por ejemplo, un bus de dirección de 32 bits puede direccionar hasta 2^32 (4.294.967.296) ubicaciones de memoria diferentes.

En resumen, mientras que el bus de datos se encarga de transferir los datos entre los componentes del sistema, el bus de dirección se utiliza para especificar la ubicación específica de memoria o de dispositivos a los que se desea acceder. Ambos buses son esenciales para el funcionamiento adecuado y eficiente de un sistema informático, permitiendo la comunicación y la gestión de datos de manera coordinada y rápida.

## 6. Memoria
[Guiding concepts: Data storage and memory](https://www.ibm.com/think/topics/central-processing-unit)

Memory is an allocation of computer files from which specific operating instructions or other forms of digital information can be extracted and utilized. Memory usually takes the form of short-term storage for the files most often accessed during recent computer use. When a piece of data first enters an operating system (OS), it’s placed within that OS’s random-access memory (RAM).

## 7. Opcode 
[Opcode: tomado de chatGPT](https://chatgpt.com/)

En informática, un código de operación u opcode (acrónimo inglés de operation code) es la porción de una instrucción de lenguaje de máquina que especifica la operación a ser realizada. Su especificación y formato serán determinados por la arquitectura del conjunto de instrucciones (ISA) del componente de hardware de computador - normalmente un CPU, pero posiblemente una unidad más especializada.


## Descripción

En este modelo de computadora, encontramos 3 bloques principales: dos de memoria, separados, el ROM y la memoria; y la CPU. Además, se puede evidenciar, una señal de reloj con la frecuencia del procesador. 

Dentro de la memoria ROM, en la cual se almacena el programa, podemos encontrar dos registros: el registro A, encarcado de mostrarnos la dirección donde se tiene que buscar la instrucción; y el registro D, encargado de recuperar el dato de la instrucción. 

Por otro lado, la otra memoria, guarda los datos con los que se va operar. 

La CPU, es el cerebro del computador, y es el encargado de encontrar la instrucción y desarrollarla. 

## Punto 4
Esa instrucción manda a que se busque en la RAM el 16384, y se quedé concentrado en esa dirección, pero sin aún mandarla al registro D, pues esto no se ha pedido. 

Fetch: va y busca la instrucción , en la dirección que le mande el pc

Decode: decodifica, es decir, ve que tipo de operacion tiene que realizar, es tipo A o tipo C? y las manda a las compuertas correspondientes para luego ser ejecutadas. 

## Instrucciones tipo A y C
Instrucciones tipo A: Estas instrucciones SIEMPRE hacen lo mismo: almacenan en el circuito de la CPU los 15 bits menos significativos de la instrucción. ¿En dónde se almacenan esos bits?, en una memoria interna de la CPU llamada REGISTRO A.

Instrucciones tipo C: son instrucciones cuyo bit de mayor peso es 1.
Con este tipo de instrucciones se pueden realizar 3 cosas: operaciones, indicar un destino, y saltos.

En general una instrucción tipo C se representa en lenguaje ensamblador así:`destino=operación;salto`
las instrucciones tipo C codifican MUCHAS funciones. Cada uno de los 16 bits de la instrucción tipo C sirve para indicar qué debe hacer la CPU. 
las operaciones son muy variadas, desde invertir los bits del registro D y A, hasta realizar operaciones como D+, A-1, etc. 


## Notas

le caben hasta un tamaño de 256. Sin embargo números permitidos se pueden rotar y quedar de mayor tamaño.
----> 8 bits 
máximo valor inmediato, que se utiliza con # antes ---> 8 bits = 256 

lsr = logic shift right --> solo lo desplaza, sin importar el 1 o 0 de negativo o positivo. llena de ceros lo que está a la derecha. 
lsl = logic shift left

asr = aritmetic shift right --> tiene en cuenta el signo del númemro que está rotando
asl = aritmetic shift left

ror = aparte que lo desplaza a la derecha, lo que se bota lo pasa al principio 

movs = lo unico adicional aparte de mover, es que me actualiza el registro de estado

Toca de por partes, para meterlo a un registro: 
movw = mueve un numero de 16 bits directamente a la parte baja del registro seleccionado  ; 0x1234
movt = mueve directamente un número de 16 bits a la parte baja de un registro : los 4 bytes más significativos; 0x5678

Todas estas operaciones son de registros a registros. 


str = guarda (store) en la RAM
strb = del tamñado de un byte. lo que está en R2, guaárdelo en la direccion de la RAM de R0 (lo que aparezca en este registro) +4
este más 4 es la siguiente direccion de memoria

123 654
donde cada 2, 00: 1

strh = 16 bits

origen [destino # más número a la dirección] ---> entre corchetes, direccion de la memoria RAM

tamaños: 
word = 32 bits
halfword = 16 bits 

ldr  = lee un dato de un registro y lo guarda en algun otro registro, más unval
se necesita usa esta funcion cuando son con variables creadas que son muy grandes
ejemplo: 

// Definición de constantes usando .equ
.equ BASE_ADDRESS, 0x20000000
.equ VALUE1, 10
.equ VALUE2, 20

_start:
    // Inicialización de registros usando las constantes definidas
    LDR R0, =BASE_ADDRESS   // R0 = Dirección base de la memoria
    MOV R1, #VALUE1         // R1 = 10

