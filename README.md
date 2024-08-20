# Aprender_eBPF_español
Liz Rice Learning eBPF spanish translation 



Repositorio para acompañar el libor Learning eBPf(publicado por O'reilly)

copia cortesia de [isovalent] (https://isovalent.com/books/learning-ebpf/)
Ejecutando los ejemplos del codigo

Se incluyen los ejemplos de los programas eBPF dados en el libro

Se incluye el archivo de configuración de Lima que se requiere para construir el codigo pre-instalado
No es necesario si se usa una maquina con Linux ya sea instalod o en una MV.
Se usara el archivo learning-ebpf.yaml como guia de instalación de los paquetes que se requieran.
La version del kernel varia entre capitulo y capitulo.

Prerequisitios : kernel 5.15
Todos ejemplo fueron probadas en Fedora 39 con un kernel 6.10.3-100.fc39.x86_64
Instalar el repositorio

git clone --recurse-submodules https://github.com/lizrice/learning-ebpf
cd learning-ebpf

Crear libbpf e instalar los archivos de cabecera(header files)

cd libbpf/src
make install 
cd ../..

Construir `bfptool`

Hay varios ejemplos usando bpftool

## Ejemplos
Cada directorio corresponden a su respectivo capítulo del libro.

A continuación se muestran los diferentes ejemplos que acompañan a cada capítulo.

    * Capítulo 1: ¿Qué es eBPF y por qué es importante?
    * Capítulo 2: "Hola mundo" de eBPF: ejemplos básicos que utilizan el marco BCC.
    Capítulo 3: Anatomía de un programa eBPF: ejemplos de XDP basados ​​en C, utilizados en el libro para explorar cómo el código fuente se transforma en código de bytes y código de máquina de eBPF. También hay un ejemplo de llamadas a funciones de BPF a BPF.
    Capítulo 4: La llamada al sistema bpf(): más ejemplos basados ​​en BCC, utilizados en el libro para ilustrar lo que sucede en el nivel de llamada al sistema cuando usa eBPF.
    Capítulo 5: CO-RE, BTF y Libbpf: código de ejemplo en C basado en Libbpf.
    Capítulo 6: El Verificador eBPF - ¡Realice pequeñas ediciones en el código de ejemplo para provocar una variedad de errores del verificador!
    Capítulo 7: Programa eBPF y tipos de archivos adjuntos: ejemplos de diferentes tipos de programas eBPF.
    Capítulo 8: eBPF para redes: código de ejemplo que se conecta a varios puntos de la pila de red para interferir con las solicitudes de ping y curl. Próximamente, ejemplo de balanceador de carga
    Capítulo 9: eBPF para seguridad (próximamente)
    Capítulo 10: Programación eBPF: el libro explora ejemplos de varias bibliotecas eBPF.
    Capítulo 11: La evolución futura de eBPF

No hay ejemplos de código para los Capítulos 1 y 11.
Privilegios
Necesitará privilegios de root (bueno, estrictamente `CAP_BPF` y privilegios adicionales) para poder cargar programas `BPF` en el kernel. `sudo` -s es tu amigo.

Ver resultados de seguimiento(trace) de eBPF

Un par de formas de ver el resultado del canal de seguimiento del kernel donde se escribe el seguimiento de eBPF:

 `cat /sys/kernel/debug/tracing/trace_pipe`
 `bpftool prog tracelog`







