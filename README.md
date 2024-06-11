TP 3
Russo Alexia

1a_ Con respecto a los tiempos va variando los tiempos de ejecucion.

1b_ NO. No son iguales, cambian.

1c_ Sacar esas líneas hace un retardo que puede mitigar los efectos de condiciones de carrera, es un comportamiento más consistente del programa.

2b_ 
![Screenshot_1](https://github.com/AleeeR12/ASO2024TPs/assets/130691034/a2b26368-79b2-4378-81b4-0ffe3ec24fbc)


1_ A: Region critica  B: Se bloquea
2_ A: Agarra una hamburguesa  B: Bloqueado
3_ A: Se lleva la hamburguesa  B: Sigue bloqueado
4_ A: Sale de la region critica  B: Intenta entrar
5_ B: Obtiene permiso y entra  A: Espera afuera 
6_ B: Agarra la hamburguesa  A: Espera
7_ B: Se lleva la hamburguesa  A: Sigue esperando
8_ B: Sale de la Region critica  A: Intenta entrar

2a_
```
#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>
#define NUMBER_OF_THREADS 2
#define CANTIDAD_INICIAL_HAMBURGUESAS 20
int cantidad_restante_hamburguesas = CANTIDAD_INICIAL_HAMBURGUESAS;
int turno = 0;

void *comer_hamburguesa(void *tid)
{
    while (1 == 1)
    { 
        while (turno != (int) tid);
        // INICIO DE LA ZONA CRÍTICA
        if (cantidad_restante_hamburguesas > 0)
        {
            printf("Hola! soy el hilo(comensal) %d , me voy a comer una hamburguesa ! ya que todavia queda/n %d \n", (int) tid, cantidad_restante_hamburguesas);
            cantidad_restante_hamburguesas--; // me como una hamburguesa
        }
        else
        {
            printf("SE TERMINARON LAS HAMBURGUESAS :( \n");
        turno = (turno + 1) % NUMBER_OF_THREADS;
            pthread_exit(NULL); // forzar terminacion del hilo
        }
        // SALIDA DE LA ZONA CRÍTICA
turno = (turno + 1) % NUMBER_OF_THREADS;   
    }
}

int main(int argc, char *argv[])
{
    pthread_t threads[NUMBER_OF_THREADS];
    int status, i, ret;
    for (int i = 0; i < NUMBER_OF_THREADS; i++)
    {
        printf("Hola!, soy el hilo principal. Estoy creando el hilo %d \n", i);
        status = pthread_create(&threads[i], NULL, comer_hamburguesa, (void *)i);
        if (status != 0)
        {
            printf("Algo salio mal, al crear el hilo recibi el codigo de error %d \n", status);
            exit(-1);
        }
    }

    for (i = 0; i < NUMBER_OF_THREADS; i++)
    {
        void *retval;
        ret = pthread_join(threads[i], &retval); // espero por la terminacion de los hilos que cree
    }
    pthread_exit(NULL); // como los hilos que cree ya terminaron de ejecutarse, termino yo tambien.
}
```
