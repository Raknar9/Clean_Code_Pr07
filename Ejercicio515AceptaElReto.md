## Ejercicio 515 de aceptaelreto.com

### El siguiente codigo se podria decir que incumple algunas reglas del clean code

````
public class ejercicio515 {
    static int getTurnos(int n, int turno) {
        if (n <= 0) return 0;
        if (turno == 1) return getTurnos(n - 1, 2) + 1;
        if (n % 2 == 0) return getTurnos(n - 2, 1) + 1;
        return getTurnos(n - 1, 1) + 1;
    }

    public static void main(String[] args) {

        Scanner s = new Scanner(System.in);

        int copas;

        while (true) {
            copas = s.nextInt();
            if (copas == 0) break;
            System.out.println( getTurnos(copas, 1) );
        }

    }
}

````
## Algunas de las reglas que incumple podrian ser los siguientes:

- Nombres poco descriptivos: los nombres de las variables y funciones no son descriptivos y no ayudan a entender qué hace el código.

- Uso de "magic numbers": el código utiliza números "mágicos" sin explicación, como el número 1 y 2 en las funciones getTurnos().

- Función demasiado larga: la función getTurnos() es demasiado larga y realiza varias acciones diferentes. Sería mejor separarla en funciones más pequeñas y descriptivas.

- Uso excesivo de condiciones anidadas: la función getTurnos() utiliza varias condiciones anidadas, lo que puede dificultar la comprensión del código.

- Falta de formato: el código no sigue un formato consistente, lo que dificulta su lectura y comprensión.

- Nombres de variables poco descriptivos: las variables "n" y "turno" no indican claramente su propósito.

- Función con una estructura compleja: la función "getTurnos" tiene una estructura compleja con varios condicionales anidados, lo que dificulta su lectura y comprensión.

## El siguiente codigo podria decirse que esta mejor estructurado ,corrigiendo algunos errores para una mejor comprension del codigo.

````
public class ejercicio515Corregido {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        int numCopas;

        while (true) {

                numCopas = scanner.nextInt();
                if (numCopas == 0) break;
                System.out.println(getTurnos(numCopas, 1));


                scanner.nextLine();
            }
        }
    static int getTurnos(int numCopas, int turnoActual) {
        if (numCopas <= 0) return 0;
        if (turnoActual == 1) return getTurnosCuandoEsElTurnoUno(numCopas);
        if (esPar(numCopas)) return getTurnosCuandoEsPar(numCopas);
        return getTurnosCuandoEsImpar(numCopas);
    }
    static int getTurnosCuandoEsElTurnoUno(int numCopas) {
        return getTurnos(numCopas - 1, 2) + 1;
    }
    static int getTurnosCuandoEsPar(int numCopas) {
        return getTurnos(numCopas - 2, 1) + 1;
    }
    static int getTurnosCuandoEsImpar(int numCopas) {
        return getTurnos(numCopas - 1, 1) + 1;
    }
    static boolean esPar(int num) {
        return num % 2 == 0;
    }
}

````