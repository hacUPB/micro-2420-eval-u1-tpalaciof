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

ldr  = lee un dato de un registro y lo guarda en algun otro registro, más unval ---> ejem: Lo toma de la memoria y lo guarda

MOV R3, #0x20000000 // R3 = Dirección base de la memoria

// Almacenar los resultados en memoria
    STR R4, [R3]       // Almacena R4 en la dirección apuntada por R3

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

### Operaciones matemáticas

// Operaciones Aritméticas

    // Suma: R4 = R0 + R1
    ADD R4, R0, R1

    // Resta: R5 = R0 - R2
    SUB R5, R0, R2

    // Multiplicación: R6 = R0 * R2
    MUL R6, R0, R2

    Más eficiente para restarle un valor al propio registro: 

    ---> add R0, R0, #-1
    qu: sub R0, R0, #1


----------------------------
## Máscara
## forzar bits a 1 (OR)
un 1 en la máscara cambia los bits a 1 (si ya era 1, se queda en uno)
un 0 no cambia nada 

orr = 

## forzar bits a 1 (AND)
un 0 en la máscara cambia un 1 a 0, o el cero lo deja en cero

(MVN = NOT)

MVN R0, R0 
AND R2, R1, R0

o sólamente: 
BIC R2, R1, R0 ----> lo niega, y lo cambia 

## conmutar el valor de un bit (XOR)
mismo estado en ambas: 0
diferente estado en ambas: 1
EOR R3, R0


// Operación AND para forzar bits a cero
MOVW R1, #MASK_AND     // R1 = 0000111100001111 en binario
AND R2, R0, R1        // R2 = R0 AND R1, resultado: 0000000000000000

// Operación OR para forzar bits a uno
MOVW R3, #MASK_OR      // R3 = 0000000011111111 en binario
ORR R4, R0, R3        // R4 = R0 OR R3, resultado: 1111000011111111

// Operación XOR para invertir bits específicos
MOVW R5, #MASK_XOR     // R5 = 0000111111110000 en binario
EOR R6, R0, R5        // R6 = R0 XOR R5, resultado: 1111111100000000

// Operación NOT para complementar bits
MVN R7, R0            // R7 = NOT R0, resultado: 0000111100001111



// Operación BIC para borrar bits específicos

donde esté un 1 en la máscara borra el bit: 

MOVW R8, #MASK_BIC     // R8 = 1111000000001111 en binario
BIC R9, R0, R8        // R9 = R0 BIC R8, resultado: 0000000011110000

001101111111
      010101   ---> MASK
------------
001101101010   ---> 0x36A

BIC R1,R0, MASK

## saltos

LR: 
STACK: el que entra de primero sale de último (LIFO)

bx : copia en el pc el contenido del registro que se pone a continuacion

bxeq lr ---> pongame en el pc el contenido de lr , si es cero
b contador2 --->> si no es cero, vuelve a ejecutarse una vez más el ciclo

push{lr}: acá se guarda el LR en el STACK porque la siguiente instrucción que es un BL puede borrar el LR con un nuevo valor y no existirá forma de regresar ----> es como mandarlo a la memoria RAM a una zona que se llama el STACK

pop: saco de la pila del STACK y lo pone en el registro {}


### ejemplo1
copiar en la memoria 0x20000000 los valores del 1 al 20
.syntax unified
.global _start
.text

_start:
 mov R0, #0x20000000
 mov R1, #0
 mov R2, #20
 
contador: 

add R1,R1,#1
STR R1, [R0],#4 ---> a la direccion le suma el valor en cada loop
adds R2, R2, #-1	// se tiene que poner la s para que sepa que la inmediatamente anterior es 0, si lo es 
beq end
b contador // si no es cero, vuelve a ejecutarse una vez más el ciclo

// Bucle infinito para detener la ejecución
end:
B .
.end

### ejemplo2
.syntax unified
.global _start
.text
s
.equ v1, 0x20000100
.equ v2, 0x20000140
.equ vRes 0x2000200

vec1:  //definiendo una equiqueta ---> luego el procesador la definirá como una dirección de memoria en la flash
.hword 1, 2, 3, 4, 0xFAFA	//lo último solo indica que se acabó  

vec2: 
.hword 2, 3, 4, 5, 0xFAFA

_start:
 mov R0, #0x20000000
 mov R1, #0
 mov R2, #20
 
contador: 

end:
B .
.end


## 09/08/2024

Procesador MK18F
* Resistencias pull-up y pull-down: se necesita establecer un valor lógico inicial para que tengan un valor lógico establecido
* Todos los registros son de 32 bits
* Adress = base adress + 0h offset + (4d x i), where i = 0d to 34d

* Todos los perifericos necesitan del clock para funcionar ---> el puerto también es un periférico

## 14/08/2024
/*********************************************************************
*                    SEGGER Microcontroller GmbH                     *
*                        The Embedded Experts                        *
**********************************************************************
*                                                                    *
*            (c) 2014 - 2022 SEGGER Microcontroller GmbH             *
*                                                                    *
*       www.segger.com     Support: support@segger.com               *
*                                                                    *
**********************************************************************
*                                                                    *
* All rights reserved.                                               *
*                                                                    *
* Redistribution and use in source and binary forms, with or         *
* without modification, are permitted provided that the following    *
* condition is met:                                                  *
*                                                                    *
* - Redistributions of source code must retain the above copyright   *
*   notice, this condition and the following disclaimer.             *
*                                                                    *
* THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND             *
* CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES,        *
* INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF           *
* MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE           *
* DISCLAIMED. IN NO EVENT SHALL SEGGER Microcontroller BE LIABLE FOR *
* ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR           *
* CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT  *
* OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;    *
* OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF      *
* LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT          *
* (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE  *
* USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH   *
* DAMAGE.                                                            *
*                                                                    *
*********************************************************************/

/*********************************************************************
*
*       _start
*
*  Function description
*  Defines entry point for an MKE18F16 assembly code only
*  application.
*
*  Additional information
*    Please note, as this is an assembly code only project, the C/C++
*    runtime library has not been initialised. So do not attempt to call
*    any C/C++ library functions because they probably won't work.
*/

 .syntax unified
 .global _start
 .text

 // -------------------------RELOJ PERIFÉRICOS----------------------
 .equ    PCC_BASE, 0x40065000
 .equ    PCC_PORTA_OFFSET, 0x124
 .equ    PCC_PORTB_OFFSET, 0x128
 .equ    PCC_CGC_BIT, 30

 // -------------------DIRECCIONES DE LOS PUERTOS-------------------- 
 //PTA 2: LED
 .equ    PORTA_BASE, 0x40049000
 .equ    PORTA_PCR2_OFFSET, 0x8

 //PTB 9: Pulsador
 .equ    PORTB_BASE, 0x4004A000
 .equ    PORTB_PCR9_OFFSET, 0x24

 // Activar el Mux
 .equ   PORT_PCR_MUX_BITS, 0x8 //-->001---> 1 bit en el bit 8
//Se pone un 1 en un registro y se mueve 8 veces a la izquierda

// Address: Base address + 0h offset + (4d × i), where i=0d to 31d

 .equ    GPIOD_BASE, 0x400FF0C0
 .equ    GPIOD7_OFFSET, 7
 .equ    GPIO_DDR, 0x14
 .equ    GPIO_PDOR, 0x0
 .equ    GPIO_PDIR, 0x10

 .thumb_func

_start:
        bl  init_clks
        bl  init_ports
        bl  init_gpio
loop:
        adds    r0, r0, #1
        b       loop

init_clks:
    ldr     r4, =#PCC_BASE
    ldr     r5, =#PCC_PORTA_OFFSET
    mov     r0, #1
    lsl     r0, #PCC_CGC_BIT        //en el bit 30,lo activa
    str     r0, [r4, r5]            // lo activa para el Puerto A
    ldr     r5, =#PCC_PORTB_OFFSET  //offset del puerto B
    str     r0, [r4, r5]            // lo activa para el puerto B
    bx      lr                      // hace que el registro pc sea lr

init_ports:
    ldr     r4, =#PORTA_BASE    //toma de la memoria la direccion del puerto A base y lo guarda en el registro R4
    mov     r0, #1              // agrega la constante en r0
    lsl     r0, #PORT_PCR_MUX_BITS // mueve este 1, 8 veces a la izquierda
    ldr     r5, =#PORTD_PCR7_OFFSET   
    str     r0, [r4, r5]
    ldr     r5, =#PORTD_PCR6_OFFSET
    orr     r0, #3    //Como la mascara 10000011, agrega este 11 al final
    str     r0, [r4, r5]  // pone el valor de r0 = 10000011 en PORTD_PCR6, activa el mux, el DS y el DE
    bx      lr

init_gpio:
    ldr     r4, =#GPIOD_BASE
    mov     r0, #1
    lsl     r0, #GPIOD7_OFFSET  
    ldr     r5, =#GPIO_DDR  // DDR: establece dicha posición como salida o entrada
    ldr     r1, [r4, r5]  //[r4, r5] es la direccion del DDR, guarda lo que haya en esa direccion en r1
    orr     r0, r1        //a esa dirección, establece como salida lo que invierte comparandolo con r0
    str     r0, [r4, r5]  // guarda lo que quedo en r0, en la direccion del DDR
    bx      lr

    
leer_pulsador:
    ldr     r4, =#GPIOD_BASE
    ldr     r0, [r4, #GPIO_PDIR]
    lsr     r0, #GPIOD7_OFFSET
    ands    r0, #1
    bx      lr

escribir_led:
    ldr     r4, =#GPIOD_BASE
    ldr     r1, [r4, #GPIO_PDOR]
    lsl     r0, #GPIOD7_OFFSET
    orr     r0, r1
    str     r0, [r4, #GPIO_PDOR]
    bx      lr
