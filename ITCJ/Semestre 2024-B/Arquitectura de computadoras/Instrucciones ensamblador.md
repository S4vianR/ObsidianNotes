Materia: Arquitectura de computadoras [[Arquitectura de computadoras]]


### Mostrar un mensaje
```asm
.data
msg1 db 'Hoy es juebebes $'

.code
mov ah, 09h
lea dx, msg1
int 21h
```

### Mostrar un caracter
```asm
mov ah, 02h
mov dl, ? ; Lo que se imprima
int 21h
```

### Capturar con echo y lo leído se guarda en "al"
```asm
org 100h

.code
mov ah, 01h
int 21h
```

### Mover el cursor
```asm
mov ah, 02h
mov dh, 0 ; num. renglon
mov dl, 0 ; num. columna
mov bh, 0 ; num. pagina de memoria
int 10h
```

### Limpiar pantalla
```asm
mov ah, 00h
mov al, 03h
int 10h
```

```asm
mov ax, 0003h
int 10h
```

## Demas instrucciones
AAM = Hexa -> Dec
AAD = Dec -> Hexa

## Arreglos
CX -> Es el registro contador
SI -> Es el registro del índice

## Salto de linea
```asm
; Salto de linea
mov ah, 02h
mov dl, 0AH ; Nueva linea
int 21h    

mov ah, 02h
mov dl, 0DH ; Regresa el cursor al inicio del renglon
int 21h
```

## Espacio en linea
```asm
; Espacio
mov ah, 02h
mov dl, 20h
int 21h 
```

