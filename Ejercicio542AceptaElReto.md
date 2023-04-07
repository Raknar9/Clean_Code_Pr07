## Ejercicio 542 de Aceptaelreto.com
### El siguiente codigo incumple algunas de las reglas del clean code
````
public class ejercicio542 {
    public static void main(String[] args) {

        Scanner s = new Scanner(System.in);

        int casos = s.nextInt();
        boolean sirve;
        ArrayList<Integer> list1 = new ArrayList<>();
        ArrayList<Integer> list2 = new ArrayList<>();

        while (casos-- != 0) {
            for (int i = 0; i < 3; i++) list1.add(s.nextInt());
            for (int i = 0; i < 3; i++) list2.add(s.nextInt());
            Collections.sort(list1);
            Collections.sort(list2);
            if (list1.get(2) < list2.get(2)) {
                if (list1.get(1) < list2.get(1)) {
                    if (list1.get(0) < list2.get(0)) {
                        sirve = true;
                    }
                    else sirve = false;
                }
                else sirve = false;
            }
            else sirve = false;
            System.out.println( sirve ? "SIRVE" : "NO SIRVE" );
            list1.clear();
            list2.clear();
        }

    }
}

````
### Algunas de las reglas que incumplen podrian ser 
- La variable sirve no tiene un nombre descriptivo y no está inicializada, lo que hace que su uso posterior sea confuso.

- Las variables list1 y list2 tienen nombres poco descriptivos. Además, el nombre de la clase ArrayList no está capitalizado correctamente.

- La estructura if-else anidada es difícil de leer y de entender.

- No se están utilizando llaves {} para delimitar los bloques de código de las estructuras de control, lo que puede llevar a errores y confusiones.

### Se podra observar los posibles cambios que se pueden hacer al codigo para cumplir algunas reglas y mejorar la estructura del codigo.

````
public class ejercicio542Corregido {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        int casos = scanner.nextInt();
        boolean esValido;
        List<Integer> dimensiones1 = new ArrayList<>();
        List<Integer> dimensiones2 = new ArrayList<>();

        while (casos-- != 0) {
            for (int i = 0; i < 3; i++) {dimensiones1.add(scanner.nextInt());}
            for (int i = 0; i < 3; i++) {dimensiones2.add(scanner.nextInt());}

            Collections.sort(dimensiones1);
            Collections.sort(dimensiones2);

            esValido = (dimensiones1.get(0) < dimensiones2.get(0)) && (dimensiones1.get(1) < dimensiones2.get(1)) && (dimensiones1.get(2) < dimensiones2.get(2));

            if(esValido)
            {
                System.out.println("SIRVE");
            }else {
                System.out.println("NO SIRVE");
            }
            

            dimensiones1.clear();
            dimensiones2.clear();
        }


    }
}

````