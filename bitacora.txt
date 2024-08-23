# Ejercicio 1
.syntax unified
.global _start
.text

.equ diri, 0x20000800
.thumb_func
_start:
    bl  guardar_datos
    bx  lr

guardar_datos:
    ldr   r4, =diri 
    mov   r0, #50     // Inicializa el primer número a guardar
    mov   r1, #140    // Último número a guardar
loop_guardar:
    str   r0, [r4], #4 // Guarda el número en la memoria y avanza a la siguiente posición
    adds  r0, #10     // Incrementa el número en 100 para el siguiente ciclo
    cmp   r0, r1       // Compara si se ha alcanzado el último número
    ble   loop_guardar // Si no se ha alcanzado el último número, continuar guardando
    bx    lr           // Retorna

# Ejercicio 2 

.syntax unified
.global _start
.text

.thumb_func
_start:
    bl  init            // bl: entra a la subrutina de init ---> se actualizó el lr a la direccion de retorno
    bl  cargar_memoria  // de la ejecucion
loop:
    bl  copiar_datos
    b   loop

init:
    mov   r0, #0        // se asegura que los valores iniciales de los registros sea 0
    mov   r1, #0        // Sin embargo es algo un poco inutil, porque en las lineas siguiente se cambian
    mov   r2, #0        // estos valores. Además nunca se utiliza el r2. Mejor no poner esta subrutina
    bx    lr            // bx: salta a la direccion de lr

cargar_memoria:           
    ldr   r4, =#0x20000000  // almacena los valore en los registros
    mov   r0, #1            // valor que será guardado en las distintas direcciones
    mov   r1, #10           // valor máximo de iteraciones, que se irá restando de a uno en loop_carga

loop_carga:
    str   r0, [r4], #4   // almacena lo guardado en r0, en la direccion guardada en r4, +4 en cada iteracion
	  adds  r1, #-1      // suma r1 = r1-1 y actualiza la bandera. 
    beq   fin_carga      // beq: Salta si el resultado de la comparación es igual a cero ---> si lo anterior
    b     loop_carga     // (la bandera) es cero (la bandera Z = 1, cuando es 0)
                            // b: si esto no pasa, salta una vez más al loop_carga
fin_carga:
    bx    lr            // una vez se haya acabado el loop carga, el programa se dirige aquí, y vuelve donde 
                        // estaba el lr, en este caso, para entrar a "loop"
copiar_datos:
    ldr   r4, =#0x20000000  // guarda esta dirección en r4
loop_copia:
    ldr   r0, [r4]          // guarda el valor de r0, en la direccion almacenada en r4
    cmp   r0, #0            // cmp: compara si r0 es 0, y actualiza la bandera
    beq   fin_copia         // si es 0, termina el loop
    str   r0, [r4, #0x100]  // si no lo es, se guarda lo de r0 en la direccion almacenada en r4+4
    add   r4, #4            // añade 4 a esta direccion
    b     loop_copia
fin_copia:
    bx    lr        // se puede considerar como una falla del programa, pues no tiene mucho sentido que se  
                    // vuelva a iterar una vez más toda la funcion loop, y volver a copiar los datos una 
                    // y otra vez


# Ejercicio 3 
