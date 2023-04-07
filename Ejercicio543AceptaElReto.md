## Ejercicio 542 de Aceptaelreto.com
### El siguiente codigo incumple algunas de las reglas del clean code
````
class Sombrilla {
    double n1, n2, r;
    Sombrilla(int n1, int n2, int r) {
        this.n1 = n1;
        this.n2 = n2;
        this.r = r;
    }
}

public class ejercicio543 {

    public static void main(String[] args) {

        final Scanner s = new Scanner(System.in);

        int casos = s.nextInt();
        ArrayList<Sombrilla> sombrillas = new ArrayList<>();

        while(casos-- != 0) {
            for (int i = s.nextInt(); i > 0; i--) {
                sombrillas.add(new Sombrilla(s.nextInt(), s.nextInt(), s.nextInt()));
            }
            int res = 0;
            for (int i = 0; i < sombrillas.size(); i++) {
                Sombrilla s1 = sombrillas.get(i);
                for (int j = i + 1; j < sombrillas.size(); j++) {
                    Sombrilla s2 = sombrillas.get(j);
                    double distance = Math.sqrt(
                            ((s1.n1 - s2.n1) * (s1.n1 - s2.n1)) + ((s1.n2 - s2.n2) * (s1.n2 - s2.n2))
                    );
                    if (distance < s1.r + s2.r) res++;
                }
            }
            System.out.println( res );
            sombrillas.clear();
        }

    }

}

````

### Algunas de las reglas que incumplen podrian ser 
- Nombres de variables poco descriptivos: Las variables n1, n2 y r en la clase Sombrilla no son nombres descriptivos para los atributos que representan.

- Variables no declaradas como final: En la clase principal p543, la variable s de tipo Scanner podría declararse como final, ya que no cambia a lo largo del programa.

- Código demasiado anidado: En la clase principal p543, la lógica para calcular el número de sombrillas que se solapan está anidada en dos bucles for. Esto hace que el código sea más difícil de entender y mantener.*/

### Se podra observar los posibles cambios que se pueden hacer al codigo para cumplir algunas reglas y mejorar la estructura del codigo.

````
class sombrilla {
    double x, y, r;
    sombrilla(double x, double y, double r) {
        this.x = x;
        this.y = y;
        this.r = r;
    }
}

public class ejercicio543Corregido {

    public static void main(String[] args) {

        final Scanner scanner = new Scanner(System.in);

        int casos = scanner.nextInt();

        while(casos-- != 0) {
            List<sombrilla> sombrillas = new ArrayList<>();
            int numSombrillas = scanner.nextInt();
            for (int i = 0; i < numSombrillas; i++) {
                sombrillas.add(new sombrilla(scanner.nextDouble(), scanner.nextDouble(), scanner.nextDouble()));
            }
            int numSolapamientos = calcularSolapamientos(sombrillas);
            System.out.println(numSolapamientos);
        }

    }

    private static int calcularSolapamientos(List<sombrilla> sombrillas) {
        int numSolapamientos = 0;
        for (int i = 0; i < sombrillas.size(); i++) {
            sombrilla s1 = sombrillas.get(i);
            for (int j = i + 1; j < sombrillas.size(); j++) {
                sombrilla s2 = sombrillas.get(j);
                double distancia = Math.sqrt((s1.x - s2.x) * (s1.x - s2.x) + (s1.y - s2.y) * (s1.y - s2.y));
                if (distancia < s1.r + s2.r) {
                    numSolapamientos++;
                }
            }
        }
        return numSolapamientos;
    }

}

````