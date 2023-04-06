## Practoca Voluntaria Clave morse
### El siguiente codigo inclumple algunas reglas del clean code 
```
public class ejercicioCLAVE_MORSE {
    public static void main(String[] args) {
        int total=0;
        Scanner sc=new Scanner(System.in);
        //System.out.printf("Cuantos casos de prueba habra? ");
        int n=sc.nextInt();//se ingresa los casos de prueba que quieres
        sc.nextLine();
        String casos[]=new String[n];//se crea el array con el tamaño de casos de pruebas
        for (int i=0;i<n;i++)// se rellena el array n veces
        {casos[i]=sc.nextLine();}
        for (int i = 0; i <n ; i++) {//for para recorrer cada casilla donde esta un string
            total=0;//al terminar cada vuelta del primer for se iguala a 0 el total para empezar a contar
            for (int j = 0; j <casos[i].length() ; j++) {//for para recorrer el string
            if(casos[i].length()<1)//este if es solo para los casos donde el string este compuesto solo por un caracter
            {
                if (casos[i].charAt(j)=='A') {total=total+5;}
                else if(casos[i].charAt(j)=='S') {total=total+5;}
                else if(casos[i].charAt(j)=='I') {total=total+3;}
                else if(casos[i].charAt(j)=='?') {total=total+15;}
                else if(casos[i].charAt(j)=='!') {total=total+19;}
                else if(casos[i].charAt(j)=='B') {total=total+9;}
                else if(casos[i].charAt(j)=='C') {total=total+11;}
                else if(casos[i].charAt(j)=='D') {total=total+7;}
                else if(casos[i].charAt(j)=='E') {total=total+1;}
                else if(casos[i].charAt(j)=='F') {total=total+9;}
                else if(casos[i].charAt(j)=='G') {total=total+9;}
                else if(casos[i].charAt(j)=='H') {total=total+7;}
                else if(casos[i].charAt(j)=='J') {total=total+13;}
                else if(casos[i].charAt(j)=='K') {total=total+9;}
                else if(casos[i].charAt(j)=='L') {total=total+9;}
                else if(casos[i].charAt(j)=='M') {total=total+7;}
                else if(casos[i].charAt(j)=='N') {total=total+5;}
                else if(casos[i].charAt(j)=='O') {total=total+11;}
                else if(casos[i].charAt(j)=='P') {total=total+11;}
                else if(casos[i].charAt(j)=='Q') {total=total+13;}
                else if(casos[i].charAt(j)=='R') {total=total+7;}
                else if(casos[i].charAt(j)=='T') {total=total+3;}
                else if(casos[i].charAt(j)=='U') {total=total+7;}
                else if(casos[i].charAt(j)=='V') {total=total+9;}
                else if(casos[i].charAt(j)=='W') {total=total+9;}
                else if(casos[i].charAt(j)=='X') {total=total+11;}
                else if(casos[i].charAt(j)=='Y') {total=total+13;}
                else if(casos[i].charAt(j)=='Z') {total=total+11;}
            }
            else {//este else es para cuando el caso cuenta con mas de un caracter
                total=total+3;//se suma 3 por cada cambio de caracter
                if(j==casos[i].length()-1)
                {total=total-3;}//si se esta en el ultimo caracter no se suma 3
                if (casos[i].charAt(j)=='A') {total=total+5;}
                else if(casos[i].charAt(j)=='S')
                {total=total+5;}
                else if(casos[i].charAt(j)=='I')
                {total=total+3;}
                else if(casos[i].charAt(j)=='?')
                {total=total+15;}
                else if(casos[i].charAt(j)=='!')
                {total=total+19;}
                else if(casos[i].charAt(j)=='B')
                {total=total+9;}
                else if(casos[i].charAt(j)=='C')
                {total=total+11;}
                else if(casos[i].charAt(j)=='D')
                {total=total+7;}
                else if(casos[i].charAt(j)=='E')
                {total=total+1;}
                else if(casos[i].charAt(j)=='F')
                {total=total+9;}
                else if(casos[i].charAt(j)=='G')
                {total=total+9;}
                else if(casos[i].charAt(j)=='H')
                {total=total+7;}
                else if(casos[i].charAt(j)=='J')
                {total=total+13;}
                else if(casos[i].charAt(j)=='K')
                {total=total+9;}
                else if(casos[i].charAt(j)=='L')
                {total=total+9;}
                else if(casos[i].charAt(j)=='M')
                {total=total+7;}
                else if(casos[i].charAt(j)=='N')
                {total=total+5;}
                else if(casos[i].charAt(j)=='O')
                {total=total+11;}
                else if(casos[i].charAt(j)=='P')
                {total=total+11;}
                else if(casos[i].charAt(j)=='Q')
                {total=total+13;}
                else if(casos[i].charAt(j)=='R')
                {total=total+7;}
                else if(casos[i].charAt(j)=='T')
                {total=total+3;}
                else if(casos[i].charAt(j)=='U')
                {total=total+7;}
                else if(casos[i].charAt(j)=='V')
                {total=total+9;}
                else if(casos[i].charAt(j)=='W')
                {total=total+9;}
                else if(casos[i].charAt(j)=='X')
                {total=total+11;}
                else if(casos[i].charAt(j)=='Y')
                {total=total+13;}
                else if(casos[i].charAt(j)=='Z')
                {total=total+11;}
                else if(casos[i].charAt(j)==' ')
                {
                    total=total+5;//cuando hay un espacio se suma 5
                    total=total-6;// entonces se resta los 6 que sumaria al cambiar de caracter
                }
            }
            }
            System.out.printf(total+"\n");//sacamos por pantalla la suma total
        }
    }
}

```

### Algunas de las reglas que incumple podrian ser las siguientes

- El nombre de la clase no sigue la convención de nomenclatura de Java, que indica que los nombres de las clases deben comenzar con una letra mayúscula.

- El nombre de la clase es demasiado genérico e impreciso. Sería mejor renombrarla para reflejar el propósito del programa.

- El nombre de la variable "n" no es descriptivo y no indica su propósito. Es preferible utilizar un nombre más claro, como "numeroCasos".

- Los comentarios en el código no son muy útiles, ya que explican cosas obvias. Por ejemplo, el comentario "//for para recorrer cada casilla donde esta un string" no agrega información que no pueda ser deducida fácilmente por cualquier programador.

- El código tiene un bloque "if" dentro de un bucle "for" que se ejecuta en cada iteración del bucle. Esto es ineficiente y podría mejorarse moviendo el bloque "if" fuera del bucle.

- En lugar de utilizar una cadena larga de "else if" para determinar qué valor agregar al "total", sería mejor utilizar un mapa o una tabla hash para almacenar los valores de cada carácter en lugar de codificarlos en el código.

- El código no maneja adecuadamente los errores o excepciones que podrían ocurrir. Por ejemplo, si el usuario ingresa un valor no numérico cuando se solicita el número de casos, el programa lanzará una excepción y se detendrá. Sería mejor manejar este tipo de situaciones con una estructura de control de excepciones.

### Aqui una manera aproximada de mejoras que se le podrian hacer al codigo para que tenga la misma funcionalidad pero mejorando su estructura.
```
public class ClaveMorseCleanCde {
//metodo que calcula cuantos puntos vale cada caracter
public static int costo(String caracteres) {
int puntos = 0, guiones = 0;
for (char c : caracteres.toCharArray()) {
if (c == '-') guiones++;
else puntos++;
}
return (guiones * 3) +
puntos +
caracteres.length() - 1;
}
//inicializa el hashmap de acuerdo a los valores de cada caracter en puntos o guiones
public static void initializarMap(HashMap<Character, Integer> map) {
map.put('A',costo(".-"));
map.put('B',costo("-..."));
map.put('C',costo("-.-."));
map.put('D',costo("-.."));
map.put('E',costo("."));
map.put('F',costo("..-."));
map.put('G',costo("--."));
map.put('H',costo("...."));
map.put('I',costo(".."));
map.put('J',costo(".---"));
map.put('K',costo("-.-"));
map.put('L',costo(".-.."));
map.put('M',costo("--"));
map.put('N',costo("-."));
map.put('O',costo("---"));
map.put('P',costo(".--."));
map.put('Q',costo("--.-"));
map.put('R',costo(".-."));
map.put('S',costo("..."));
map.put('T',costo("-"));
map.put('U',costo("..-"));
map.put('V',costo("...-"));
map.put('W',costo(".--"));
map.put('X',costo("-..-"));
map.put('Y',costo("-.--"));
map.put('Z',costo("--.."));
map.put('?',costo("..--.."));
map.put('!',costo("-.-.--"));
}

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        HashMap<Character, Integer> map = new HashMap<>();
        initializarMap(map);

        int casos = sc.nextInt();
        sc.nextLine();
        int salida[]=new int[casos];
        while (casos-- != 0) {
            String[] palabras = sc.nextLine().split(" ");

            int total = 0;
            for (int i = 0; i<  palabras.length; i++) {
                String palabra = palabras[i];
                if (i > 0) total += 5;

                for (int j = 0; j < palabra.length(); j++) {
                    if (j > 0) total += 3;
                    total += map.get(palabra.charAt(j));
                }
            }
            //guardamos el total de cada caso en un array para mostrarlo una vez finalizado todos los casos
            salida[casos]=total;

        }
        for (int i = salida.length-1; i >= 0 ; i--) {
            System.out.printf(""+salida[i]+"\n");
        }

    }

}
```
Como se puede ver esta manera mas resumida la cual esta mejor estructurado que el primer ejemplo que se mostró.