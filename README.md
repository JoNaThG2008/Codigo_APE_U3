# Codigo_APE_U3

#include <stdio.h>

// Funciones
float calcularPromedioUnidad(int unidad);
float calcularACD();
float calcularAPE();
float calcularAA();
float calcularES();

// Función principal

int main() {

    float notaFinal = 0, notaCiclo;
    const int UNIDADES = 3;

    // Repetir el proceso para las tres unidades
    for (int i = 1; i <= UNIDADES; i++) {

        // Acumular el promedio obtenido en cada unidad
        notaFinal = notaFinal + calcularPromedioUnidad(i);
    }

    // Calcular el promedio final del ciclo
    notaCiclo = notaFinal / UNIDADES;

    printf("\n====================================\n");
    printf("     RESULTADO FINAL DEL CICLO\n");
    printf("====================================\n");
    printf("Nota Final: %.2f\n", notaCiclo);

    // Determinar si aprueba o no
    if (notaCiclo >= 7 && notaCiclo <= 10) {
        printf("APROBADO\n");
    }
    else if (notaCiclo < 7 && notaCiclo > 2.5) {
        printf("SUPLETORIO\n");
    }
    else {
        printf("REPROBADO\n");
    }

    printf("====================================\n");

    return 0;
}

// Calcular el promedio de una unidad

float calcularPromedioUnidad(int unidad) {

    float acd, ape, aa, es, promedioUnidad;

    printf("\n====================================\n");
    printf("        UNIDAD %d\n", unidad);
    printf("====================================\n");

    // Obtener las notas ponderadas de cada componente
    acd = calcularACD();
    ape = calcularAPE();
    aa = calcularAA();
    es = calcularES();

    // Calcular el promedio de la unidad
    promedioUnidad = acd + ape + aa + es;

    // Mostrar los resultados obtenidos
    printf("Promedio ACD: %.2f\n", acd);
    printf("Promedio APE: %.2f\n", ape);
    printf("Promedio AA: %.2f\n", aa);
    printf("Promedio ES: %.2f\n", es);
    printf("La nota Final de la Unidad %i es: %.2f\n", unidad, promedioUnidad);

    // Retornar el promedio de la unidad
    return promedioUnidad;
}

// Nota ponderada del ACD

float calcularACD() {

    int actividades;
    float nota, suma = 0, promedio, ponderado;

    // Validar el número de actividades
    do {
        printf("Ingrese las actividades ACD realizadas: ");
        scanf("%i", &actividades);

        if (actividades <= 0) {
            printf("Error, ingrese un numero de actividades valido.\n");
        }

    } while (actividades <= 0);

    // Ingresar y validar las notas
    for (int i = 1; i <= actividades; i++) {

        do {
            printf("Nota %i: ", i);
            scanf("%f", &nota);

            if (nota < 0 || nota > 10) {
                printf("Error nota no valida, ingrese la nota correctamente.\n");
            }

        } while (nota < 0 || nota > 10);

        suma = suma + nota;
    }

    // Calcular el promedio y la ponderación
    promedio = suma / actividades;
    ponderado = promedio * 0.20;

    return ponderado;
}

// Nota ponderada del APE

float calcularAPE() {

    int actividades;
    float nota, suma = 0, promedio, ponderado;

    // Validar el número de actividades
    do {
        printf("Ingrese las actividades APE realizadas: ");
        scanf("%i", &actividades);

        if (actividades <= 0) {
            printf("Error, ingrese un numero de actividades valido.\n");
        }

    } while (actividades <= 0);

    // Ingresar y validar las notas
    for (int i = 1; i <= actividades; i++) {

        do {
            printf("Nota %i: ", i);
            scanf("%f", &nota);

            if (nota < 0 || nota > 10) {
                printf("Error nota no valida, ingrese la nota correctamente.\n");
            }

        } while (nota < 0 || nota > 10);

        suma = suma + nota;
    }

    // Calcular el promedio y la ponderación
    promedio = suma / actividades;
    ponderado = promedio * 0.25;

    return ponderado;
}

// Nota ponderada del AA

float calcularAA() {

    int actividades;
    float nota, suma = 0, promedio, ponderado;

    // Validar el número de actividades
    do {
        printf("Ingrese las actividades AA realizadas: ");
        scanf("%i", &actividades);

        if (actividades <= 0) {
            printf("Error, ingrese un numero de actividades valido.\n");
        }

    } while (actividades <= 0);

    // Ingresar y validar las notas
    for (int i = 1; i <= actividades; i++) {

        do {
            printf("Nota %i: ", i);
            scanf("%f", &nota);

            if (nota < 0 || nota > 10) {
                printf("Error nota no valida, ingrese la nota correctamente.\n");
            }

        } while (nota < 0 || nota > 10);

        suma = suma + nota;
    }

    // Calcular el promedio y la ponderación
    promedio = suma / actividades;
    ponderado = promedio * 0.20;

    return ponderado;
}

// Nota ponderada del ES

float calcularES() {

    float eS, portafolioDigital;
    float promedio, ponderado, pES, pPortafolio;

    // Ingresar y validar la nota de ABP
    do {
        printf("Ingrese la nota de Aprendizaje Basado en Problemas: ");
        scanf("%f", &eS);

        if (eS < 0 || eS > 10) {
            printf("Error nota no valida, ingrese la nota correctamente.\n");
        }

    } while (eS < 0 || eS > 10);

    // Ingresar y validar la nota del portafolio
    do {
        printf("Ingrese la nota el Portafolio Digital: ");
        scanf("%f", &portafolioDigital);

        if (portafolioDigital < 0 || portafolioDigital > 10) {
            printf("Error nota no valida, ingrese la nota correctamente.\n");
        }

    } while (portafolioDigital < 0 || portafolioDigital > 10);

    // Calcular promedio del ES
    pES = eS * 0.70;
    pPortafolio = portafolioDigital * 0.30;
    promedio = pES + pPortafolio;

    //Ponderación 
    ponderado = promedio * 0.35;

    return ponderado;
}
