

# Examen-Parcial-2----Rodrigo-Mart-nez-Campos

Parte 2: Problemas de Codificación (70 puntos en total)
Ejercicio 1: Identificación de Número Positivo, Negativo o Cero
Escribe un programa en C++ que solicite al usuario ingresar un número entero. El programa deberá analizar el número ingresado e imprimir en pantalla si el número es "positivo", "negativo" o "cero". 

#include <iostream>  // entrada y salida

using namespace std;  // cin y cout

int main() {
    int numero;  // variable numero

    // Solicitar al usuario que ingrese un número
    cout << "Por favor, ingresa un número entero: ";
    cin >> numero;  // Lectura del número

    // Condicional entre positivo negativo o cero
    if (numero > 0) {
        cout << "El número " << numero << " es positivo." << endl;
    } else if (numero < 0) {
        cout << "El número " << numero << " es negativo." << endl;
    } else {
        cout << "El número es cero." << endl;
    }

    return 0;  // Fin del programa
}
Ejercicio 2: Día de la Semana
Crea un programa en C++ que solicite al usuario ingresar un número del 1 al 7. El programa deberá imprimir el nombre del día de la semana correspondiente al número ingresado (por ejemplo, 1 para lunes, 2 para martes, ..., 7 para domingo). 
#include <iostream>
using namespace std;

int main() {
    int dia;

    // número entre 1 y 7
    cout << "Ingresa un número entre 1 y 7: ";
    cin >> dia;

    // Condicional switch para introducir los 7 posibles casos
    switch(dia) {
        case 1:
            cout << "Lunes" << endl;
            break;
        case 2:
            cout << "Martes" << endl;
            break;
        case 3:
            cout << "Miércoles" << endl;
            break;
        case 4:
            cout << "Jueves" << endl;
            break;
        case 5:
            cout << "Viernes" << endl;
            break;
        case 6:
            cout << "Sábado" << endl;
            break;
        case 7:
            cout << "Domingo" << endl;
            break;
        default:
            cout << "Número inválido. Debes ingresar un número entre 1 y 7." << endl;
    }

    return 0;
}

Ejercicio 3: Cálculo de Promedio de Calificaciones
Un estudiante ha completado un curso de programación avanzada en C++. Durante el curso, ha realizado 8 ejercicios prácticos, y cada ejercicio se califica con una nota entre 0 y 10. Escribe un programa que solicite al usuario introducir las calificaciones obtenidas por el estudiante en cada uno de los 8 ejercicios. El programa deberá calcular y mostrar el promedio de las calificaciones. 

#include <iostream>
using namespace std;

int main() {
    double nota, suma = 0, promedio; //double en vez de int para números decimmales.
    
    // Ingresar calificaciones
    for (int i = 1; i <= 8; i++) {
        cout << "Ingresa la calificación del ejercicio " << i << " (entre 0 y 10): ";
        cin >> nota;

        // número entre 1 y 10
        if (nota < 0 || nota > 10) {
            cout << "Calificación inválida. Debe estar entre 0 y 10." << endl;
            i--;  // Decrementamos i para que el estudiante vuelva a ingresar la calificación
            continue;
        }

        suma += nota;  // Acumulamos la calificación en la variable 'suma'
    }

    // Calcular el promedio
    promedio = suma / 8;

    // Mostrar el promedio
    cout << "El promedio de las calificaciones es: " << promedio << endl;

    return 0;
}

Ejercicio 4: Promoción de "3 por 2" en Tienda
En una tienda se está ofreciendo una promoción en la cual el cliente puede llevarse tres artículos y pagar solo por los dos artículos más caros. Escribe un programa en C++ que solicite al usuario ingresar los precios de tres artículos y, como resultado, muestre el total que el cliente debe pagar bajo esta promoción.

#include <iostream>
#include <algorithm>  // Para usar sort

using namespace std;

int main() {
    double precio1, precio2, precio3;

    // Pedimos al usuario que introduzca los tres precios
    cout << "Ingresa el precio del primer artículo: ";
    cin >> precio1;
    cout << "Ingresa el precio del segundo artículo: ";
    cin >> precio2;
    cout << "Ingresa el precio del tercer artículo: ";
    cin >> precio3;

    // Colocar los precios en un arreglo
    double precios[3] = {precio1, precio2, precio3};

    // Ordenar los precios de menor a mayor
    sort(precios, precios + 3);

    // El cliente paga solo los dos artículos más caros
    double total = precios[1] + precios[2]; // Los dos artículos más caros están en las posiciones 1 y 2

    // Mostrar el total a pagar
    cout << "El total que debes pagar es: " << total << endl;

    return 0;
    }
