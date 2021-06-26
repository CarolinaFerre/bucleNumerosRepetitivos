# bucleNumerosRepetitivos
ejercicio de bucle for

 Realizar un programa completo que solicite al usuario que introduzca dos números enteros num1 y num2. Los números deben estar comprendidos entre 1 y 10 y ser num1 menor que num2, si esto no se cumple se solicitará nuevos datos, también se debe tratar la excepción de la entrada de un valor entero con formato erróneo. Con estos datos se imprimirá una escalera numérica según el siguiente formato:

Introduzca 1º Número:3
Introduzca 2º Número:2
>Error el 1º Número debe ser menor que le segundo
Introduzca 1º Número:3
Introduzca 2º Número:7
333
4444
55555
666666
7777777

import java.util.Scanner;
import java.util.InputMismatchException;
public class Ejercicio01
{
    // Metodo auxliar para leer enteros
    public static int leerNumeroEntre(int min, int max)
    {
        Scanner sc = new Scanner(System.in);
        int valor = 0;
        boolean error;
        do {
            error = false;
            try {
                valor = sc.nextInt();
            } catch ( InputMismatchException ex ){
                error = true;
                sc.nextLine(); // Solo el texto restante
            }
            if ( error ){
                System.out.println
                    (">Error en formato, vuela a introducir un valor entero:");
            }
            else if ( valor < min || valor > max ){
                error = true;
                System.out.println("Error el número debe estas entre "+min+ " y "+ max);
            }
        } while (error);
        return valor;
    }

    public static void main(String argv[])
    {
        boolean error ;
        int num1, num2;
        do {
            error = false;
            System.out.print("Introduzca 1º Número:");
            num1 = leerNumeroEntre(1,10);
            System.out.print("Introduzca 2º Número:");
            num2 = leerNumeroEntre(1,10);
            if ( num1 > num2 ){
                System.out.println("Error el 1º Número debe ser menor que le segundo");
                error = true;
            }
        }while ( error );       

        for (int i=num1; i<= num2; i++){
            for (int j = 1; j <= i; j++){
                System.out.print(i);
            }
            System.out.println();
        }
    }
}

