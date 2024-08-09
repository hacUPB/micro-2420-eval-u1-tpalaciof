[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/EID3BRwM)

# Actividad 1

## 1. Investigar 
### 1.1. CPU
[Central processing unit](https://en.wikipedia.org/wiki/Central_processing_unit)

is the most important processor in a given computer.Its electronic circuitry executes instructions of a computer program, such as arithmetic, logic, controlling, and input/output (I/O) operations.

[What is a central processing unit (CPU)?](https://www.ibm.com/think/topics/central-processing-unit)

central processing unit (CPU) is the primary functional component of a computer. The CPU is an assemblage of electronic circuitry that run a computer’s operating system and apps and manage a variety of other computer operations. A CPU is, essentially, the active brain of the computer. The CPU is the invisible manager inside the computer where data input is transformed into information output. It stores and executes program instructions through its vast networks of circuitry.

### 1.2. ALU
[What are the components in a CPU?](https://www.ibm.com/think/topics/central-processing-unit)

The arithmetic/logic unit (ALU) handles all arithmetic operations and logical operations. Its math functionality is based on four types of operations (addition, subtraction, multiplication and division). Logical operations typically involve some type of comparison (such as of letters, numbers or special characters) that’s tied to a particular computer action.

### 1.3. Registros
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

### 1.4. Unidad de control 
[Guiding concepts: Data storage and memory](https://www.ibm.com/think/topics/central-processing-unit)

The control unit of the CPU houses circuitry that guides the computer system through a system of electrical pulses and notifies it to execute high-level computer instructions. But despite its name, the control unit itself doesn’t control individual apps or programs; instead, it assigns those tasks as a human manager assigns particular jobs to different workers.

### 1.5. Buses de datos y de dirección 

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

### 1.6. Memoria
[Guiding concepts: Data storage and memory](https://www.ibm.com/think/topics/central-processing-unit)

Memory is an allocation of computer files from which specific operating instructions or other forms of digital information can be extracted and utilized. Memory usually takes the form of short-term storage for the files most often accessed during recent computer use. When a piece of data first enters an operating system (OS), it’s placed within that OS’s random-access memory (RAM).

### 1.7. Opcode 
[Opcode: tomado de chatGPT](https://chatgpt.com/)

En informática, un código de operación u opcode (acrónimo inglés de operation code) es la porción de una instrucción de lenguaje de máquina que especifica la operación a ser realizada. Su especificación y formato serán determinados por la arquitectura del conjunto de instrucciones (ISA) del componente de hardware de computador - normalmente un CPU, pero posiblemente una unidad más especializada.


## 2. Descripción

En este modelo de computadora, encontramos 3 bloques principales: dos de memoria, separados, el ROM y la memoria; y la CPU. Además, se puede evidenciar, una señal de reloj con la frecuencia del procesador. 

Dentro de la memoria ROM, en la cual se almacena el programa, podemos encontrar dos registros: el registro A, encarcado de mostrarnos la dirección donde se tiene que buscar la instrucción; y el registro D, encargado de recuperar el dato de la instrucción. 

Por otro lado, la otra memoria, guarda los datos con los que se va operar. 

La CPU, es el cerebro del computador, y es el encargado de encontrar la instrucción y desarrollarla. 

## 4. Fetch, Decode, Execute

Fetch: va y busca la instrucción , en la dirección que le mande el pc

Decode: decodifica, es decir, ve que tipo de operacion tiene que realizar, ¿es tipo A o tipo C? y le manda los bits a las compuertas correspondientes para luego ser ejecutadas. 

execute: ejecuta la orden

## 5 y 6. Instrucciones tipo A y C
Instrucciones tipo A: Estas instrucciones SIEMPRE hacen lo mismo: almacenan en el circuito de la CPU los 15 bits menos significativos de la instrucción. ¿En dónde se almacenan esos bits?, en una memoria interna de la CPU llamada REGISTRO A.

Instrucciones tipo C: son instrucciones cuyo bit de mayor peso es 1.
Con este tipo de instrucciones se pueden realizar 3 cosas: operaciones, indicar un destino, y saltos.

En general una instrucción tipo C se representa en lenguaje ensamblador así:`destino=operación;salto`
las instrucciones tipo C codifican MUCHAS funciones. Cada uno de los 16 bits de la instrucción tipo C sirve para indicar qué debe hacer la CPU. 
las operaciones son muy variadas, desde invertir los bits del registro D y A, hasta realizar operaciones como D+, A-1, etc. 

## 7. Compuertas lógicas de la CPU

los tres primers bits determinan si es una instrucción tipo A o tipo C, si es tipo A, su dígito más significativo empieza por 0, y si es tipo C, la instrucción empieza en 111. Por lo tanto se utiliza una compuerta lógica negadora NOT, para verificar este dígito más significativo. ¿Es tipo A? entonces pasa a ser un 1 ya se sabe que es tipo A y se acaba la operación. Con los otros 2 dígitos más significativos se hace un sistema de dos compuertas AND, que verifican si son 1 o 0; si efectivamente, son 1, y el dígito más significativo también lo es, entonces se sabe que es una instrucción tipo C. 

## 9. Programa en Assembler

Básicamente la función de este código en Assembler, es crear un contador, sirviéndose de los registros A y D. cuando tiene el símbolo @ quiere decir que se está actuando con el registro A. Mientras que cuando el código nos muestra "D =", evidentemente, está actuando para el registro D. El contador de nuestro programa será "i", que será constantemente guardado dentro de un sumador "sum", que a su vez, no puede ser mayor a 100. Siempre que esto se cumple, se va guardando "i" en "sum ", y vuelve iniciar un ciclo gracias al salto JMP. Cuando por fin sum es mayor a 100 se detiene el programa. 

los valores se van guardando en la memoria RAM, mientras que las instrucciones del programa están guardadas en la memoria ROM. El registro pc es el encargado de recorrer cada una de las ubicaciones donde están las instrucciones. Por ejemplo: pc = 2, nos muestra una ubicación en la ROM y la participación del registro pc en esta. 




# Actividad 2 

## 1.

- **Mapa de Memoria:** representación completa de todas las direcciones que la unidad de control de la CPU puede generar para acceder a diferentes tipos de memoria y periféricos. El diseño del mapa de memoria es crucial para el funcionamiento eficiente del microprocesador o microcontrolador, ya que determina cómo y dónde se accede a la memoria y a los periféricos durante la operación del sistema.

- **Bus de direcciones:** es un conjunto de líneas de comunicación que la CPU utiliza para enviar las direcciones de memoria. Cada línea del bus de direcciones representa un bit en la dirección de memoria. Por ejemplo, en la figura 1, se ilustra un bus de direcciones que va desde A0 hasta A15, lo que indica que el procesador puede generar direcciones de 16 bits 

- **Microprocesador familia 8086:** El mapa de memoria del procesador 8086 de Intel está conformado por un espacio de direcciones de 20 bits (A0…A19), lo que permite acceder a un total de  1 MB (1024K unidades) de memoria. Cada una de estas unidades es de 16 bits, permitiendo una amplia capacidad de almacenamiento y manipulación de datos.
En el 8086, las líneas de datos (D0…D7) y las líneas de direcciones (A0…A15) comparten los mismos pines, utilizando un bus de direcciones y datos multiplexado. Es decir, cuenta con una arquitectura tipo Von Neumann. Esta organización del bus de direcciones y datos multiplexado en el 8086 facilita la conexión de múltiples dispositivos y módulos de memoria, optimizando el uso de los recursos del sistema y permitiendo una arquitectura más eficiente y flexible.

- **Arquitectura de Von Neumann:** En la arquitectura de Von Neumann, también conocida como arquitectura de almacenamiento de programas, tanto los datos como las instrucciones se almacenan en la misma memoria y se accede a ellos a través del mismo bus.
Esto significa que el mapa de memoria es un espacio unificado que contiene tanto las instrucciones del programa como los datos manipulados por esas instrucciones. 

- **Arquitectura de Harvard:** tiene una separación clara entre la memoria de instrucciones y la memoria de datos. Esto implica que las instrucciones y los datos se almacenan en memorias diferentes y se accede a ellas a través de buses separados.

- **Set de Instrucciones:**
es el conjunto completo de instrucciones que un procesador puede ejecutar. Estas instrucciones son comandos que le indican al procesador qué operaciones realizar, como mover datos, realizar cálculos aritméticos, o controlar el flujo del programa.
Hay diferentes tipos de instrucciones, estas son: 
    * Instrucciones de Transferencia de Datos
    * Instrucciones Aritméticas y Lógicas
    * Instrucciones de Control de Flujo
    * Instrucciones de Manipulación de Bits

    cada una de estas instrucciones cuenta con ciertas características que las determinan: 

    * **Sintaxis:** se refiere al formato y estructura con la cual se escribe la instrucción. Incluye las reglas y el orden en que se deben colocar los diferentes componentes de la instrucción, como el opcode y los operandos. La sintaxis determina cómo el ensamblador interpreta las instrucciones escritas por el programador.
    * **Opcode (código de operación):** es la parte de la instrucción que especifica la operación que se debe realizar.
    * **Tamaño**
    * **Ciclos de Reloj**

- **Arquitecturas CISC y RISC:**
    * **CISC:** La arquitectura CISC está diseñada para minimizar la cantidad de instrucciones por programa, sacrificando el número de ciclos de reloj por instrucción. Las instrucciones en CISC son complejas y pueden realizar múltiples operaciones de bajo nivel
    **Características:**

        * **Instrucciones Complejas:** Pueden realizar múltiples tareas.
        * **Decodificación Lenta:** Debido a la complejidad de las instrucciones, la decodificación es más lenta.
        * **Tamaño de Instrucción Variable:** Las instrucciones pueden tener diferentes longitudes.
        *  **Uso de Microprogramación:** Utiliza microcódigo para implementar instrucciones complejas.

    * **RISC:** se enfoca en simplificar las instrucciones, permitiendo que cada instrucción realice una sola operación de bajo nivel y se ejecute en un único ciclo de reloj. Esto permite una mayor velocidad de procesamiento y una mayor eficiencia.
    **Características:**

        * **Instrucciones Simples:** Realizan una única tarea.
        * **Decodificación Rápida:** Las instrucciones simples permiten una decodificación más rápida.
        * **Tamaño de Instrucción Fijo:** Las instrucciones tienen un tamaño fijo, generalmente de 4 bytes.
        * **Pipeline:** Facilita la implementación de pipelines de instrucción.

## 2. Procesador ESP32
[esp32_datasheet_en.pdf](https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf)


Tipo de Arquitectura:

* **Arquitectura**: La arquitectura del ESP32 es una variante de la arquitectura Harvard, ya que tiene buses separados para instrucciones y datos, pero permite que el procesador acceda a la memoria de datos desde el espacio de direcciones de instrucciones y viceversa, lo que añade flexibilidad.

* **Procesador y Núcleos**: El ESP32 cuenta con procesadores Xtensa® single-/dual-core 32-bit LX6 microprocessor(s) y 3 nucleos: 1 nucleo a 1 a 240 MHz: 504.85 CoreMark; 2.10 CoreMark/MHz. Y dos núcleos a 240 MHz: 994.26 CoreMark; 4.14 CoreMark/MHz.

* ***Clocks* y *Timers***: además cuenta con los siguientes *clocks* y *timers*: 

    * Internal 8 MHz oscillator with calibration
    * Internal RC oscillator with calibration
    * External 2 MHz ~ 60 MHz crystal oscillator (40 MHz only for Wi-Fi/Bluetooth functionality)
    * External 32 kHz crystal oscillator for RTC with calibration
    * Two timer groups, including 2 × 64-bit timers and 1 × main watchdog in each group
    * One RTC timer
    * RTC watchdog

* **Memoria**: El ESP32 tiene un mapa de memoria dividido en varias regiones para instrucciones y datos. Posee una memoria ROM de 448 KB, una SRAM de 520 KB y 16 kB  SRAM en RTC. 


![Mapa de Memoria](image.png)
Para mostrar mejor las direcciones que corresponden a cada segmento de memoria, me valdré de una tabla presentada en el datasheet del ESP32: 

![Direcciones de Memoria](image-1.png)

Para los perifércos:

![Direcciones periféricos](image-3.png)
![Direcciones Periféricos](image-2.png)

## 3. Comparación de microprocesadores

Los microprocesadores utilizados serán: 

* Intel Core i9-11900K (x86-64)
* AMD Ryzen 9 5900X
* Apple M1

Las instrucciones que compararemos son:

* ADD (suma)
* MUL (multiplicación)
* MOV (carga de datos desde memoria)

Y los parámetros que compararemos son: 

* Longitud
* Ciclos de reloj 
* Complejidad 

Para **ADD**: 

| **Procesadores**               | **Longitud**               | **Ciclos de Reloj**            | **Complejidad**              |
|--------------------------------|----------------------------|--------------------------------|------------------------------|
| Intel Core i9-11900K (x86-64)  | 1-4 bytes                  | 1 ciclo                        | Baja                         |
| AMD Ryzen 9 5900X              | 1-4 bytes                  | 1 ciclo (mejor de los casos)   | Baja                         |
| Apple M1                       | 4 bytes (RISC)             | 1 ciclo (mejor de los casos)   | Baja                         |

Para **MUL**: 

| **Procesadores**               | **Longitud**               | **Ciclos de Reloj**            | **Complejidad**              |
|--------------------------------|----------------------------|--------------------------------|------------------------------|
| Intel Core i9-11900K (x86-64)  | 2-4 bytes                  | 3-4 ciclos (mejor de los casos)| Moderada                     |
| AMD Ryzen 9 5900X              | 2-4 bytes                  | 3-4 ciclos (mejor de los casos)| Moderada                     |
| Apple M1                       | 4 bytes (RISC)             | 3 ciclos (mejor de los casos)  | Moderada                     |

Para **MOV**: 

| **Procesadores**               | **Longitud**               | **Ciclos de Reloj**            | **Complejidad**              |
|--------------------------------|----------------------------|--------------------------------|------------------------------|
| Intel Core i9-11900K (x86-64)  | 1-5 bytes                  | 1 ciclo (mejor de los casos)   | Baja                         |
| AMD Ryzen 9 5900X              | 1-5 bytes                  | 1 ciclo (mejor de los casos)   | Baja                         |
| Apple M1                       | 4 bytes (RISC)             | 1 ciclo (mejor de los casos)   | Baja                         |

## Concluciones: 
### Longitud de las Instrucciones:

Intel y AMD: Las instrucciones pueden variar en longitud desde 1 a 5 bytes dependiendo de la instrucción específica y los operandos utilizados.
Apple M1: Utiliza un conjunto de instrucciones RISC con un tamaño de instrucción fijo de 4 bytes, lo cual simplifica la decodificación pero puede hacer un uso menos eficiente del espacio de memoria.

### Ciclos de Reloj:

ADD: Todas las arquitecturas logran ejecutar esta instrucción en un ciclo de reloj en el mejor de los casos.
MUL: Requiere más ciclos de reloj en todas las arquitecturas, con Intel y AMD típicamente tomando de 3 a 4 ciclos, mientras que el Apple M1 puede realizarla en 3 ciclos.
MOV: Es una instrucción rápida que puede completarse en un ciclo de reloj en las tres arquitecturas.

### Complejidad:

Las instrucciones ADD y MOV tienen baja complejidad en todas las arquitecturas, mientras que MUL es más compleja debido al mayor número de ciclos necesarios para su ejecución.


* Todas las arquitecturas son eficientes en la ejecución de instrucciones básicas como ADD y MOV, logrando completarlas en un solo ciclo de reloj.
* Las instrucciones de longitud fija del Apple M1 (RISC) simplifican el diseño del decodificador y pueden mejorar la eficiencia, pero pueden resultar en una menor densidad de código en comparación con las instrucciones Intel y AMD (CISC).
* En aplicaciones que dependen en gran medida de la multiplicación, las diferencias en los ciclos de reloj pueden tener un impacto notable, y el diseño eficiente de RISC de Apple podría proporcionar una ligera ventaja.

	