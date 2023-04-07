## Ejercicio 151 de Aceptaelreto.com
### El siguiente codigo incumple algunas de las reglas del clean code

```
public class ejercicio151 {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int F, num;
        boolean valid;

        while (true) {

            F = s.nextInt();
            if (F == 0) break;

            valid = true;
            for (int i = 0; i < F; i++) {
                for (int j = 0; j < F; j++) {
                    num = s.nextInt();
                    if (Math.abs(i - j) == 0) {
                        valid = valid && num == 1;
                    }
                    else {
                        valid = valid && num == 0;
                    }
                }
            }

            if(valid)
                System.out.println("SI");
            else{
                System.out.println("NO");
            }
            //System.out.println( valid ? "SI" : "NO" );
        }

    }
    }
```
### Algunas de las reglas que incumplen podrian ser 
- La declaración de las variables en la misma línea no es recomendable. Esto hace que el código sea difícil de leer y comprender. Se recomienda declarar una variable por línea.

- El uso de abreviaturas como 'F' para la variable que almacena la dimensión de la matriz no es descriptivo y dificulta la comprensión del código.

- La falta de comentarios para explicar el propósito del código y la lógica.

- El uso de un bucle infinito 'while (true)' sin comentarios para explicar su propósito.

- El uso de expresiones condicionales complejas dentro del bucle for, lo que dificulta la legibilidad del código.

### Se podra observar los posibles cambios que se pueden hacer al codigo para cumplir algunas reglas y mejorar la estructura del codigo.
```
public class ejercicio151Corregido {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int dimension;
        boolean valid;
        //un bucle infinito quqe seguira hasta que se indique que pare
        while (true) {

            dimension = scanner.nextInt();
            if (dimension == 0) break; // aqui en el caso de que la dimension de la matriz sea 0 , se saldra del bucle infinito

            valid = true; //si es distinto de cero podra la variable booleana a true
            //recorrera el array para comprobar que es una matriz identidad
            for (int i = 0; i < dimension; i++) {
                for (int j = 0; j < dimension; j++) {
                    int num = scanner.nextInt();
                    if (i == j) {
                        valid = valid && num == 1;
                    } else {
                        valid = valid && num == 0;
                    }
                }
            }
            // mostrara el mensaje si es o no una matriz identidad
            if(valid)
                System.out.println("SI");
            else{
                System.out.println("NO");
            }
        }

        scanner.close();
    }
}
```