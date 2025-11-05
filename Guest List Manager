/*
Author: <Tarek alharstani>

Study program: <DT>
*/
import java.util.Scanner;
public class U1 {// DA339A_U1
    static Scanner input = new Scanner(System.in);
    static String[][] gastlistan = {
            {"Adam Ason", "35"},
            {"Berta Bson", "70"},
            {"Ceasar Cson", "12"},
            {"",""},
            {"",""},
            {"",""},
            {"",""},
            {"",""},
            {"",""},
            {"",""},
    };

    public static void printMenu() {
        System.out.println("Välja för att visa gästlistan");
        System.out.println("--*--*--*--*--*");
        System.out.println("1_ printGästlista");
        System.out.println("2_printStatistics ");
        System.out.println("3_ Addagäst");
        System.out.println("4_ BytaÅlderförGäst");
        System.out.println("5_ BytaPlats");
        System.out.println("6_ BytaNamnförGäst ");
        System.out.println("7_ TabortGäst");
        System.out.println("-1_ Går ur programmet ");
    }

    public static void printGastlista() {
        for (int D = 0; D < gastlistan.length; D++) {
            for (int Q = 0; Q < gastlistan[D].length; Q++) {
    // denna loop kommer att köra kodblocket inuti den för varje värde av Q från 0 till längden av arrayen på position D i arrayen gästlistan. Varje iteration kommer att öka värdet av C med 1.
                System.out.println(gastlistan[D][Q]); // skriver ut allt som är sparat i indexet ( Föramn+ efternamn + ålder)
            }
        }
        System.out.println();
    }

    public static int Antalgaster() {
        int counter = 0;
        for (int R = 0; R < gastlistan.length; R++) {
            if (!gastlistan[R][0].equals("")) {// jämmför om värdet som finns  i arrayen gästlistan inte är lika med (antalgäster)
                counter++;
            }
        }
        return counter;
    }

    public static void printStatistics() {
        System.out.println("Du valde att skriva ut statistik");
        System.out.println("antal gäster:   " + (Antalgaster()));
        int[] vuxnaOchBarn = VuxnaOchbarn();
        System.out.println("antal vuxna:   " + vuxnaOchBarn[1]);
        System.out.println("antal barn: " + vuxnaOchBarn[0]);
        int[] aldstaOchYngsta = AldstagastenOchYngstagasten();
        System.out.println("Äldsta gästen:   " + gastlistan[aldstaOchYngsta[1]][0] + ", " + gastlistan[aldstaOchYngsta[1]][1]);
        // [1]][0] hämtar förnamnet på den äldsta gästen,  [1]][1]Detta hämtar efternamnet på den äldsta gästen
        System.out.println("Yngsta gästen: " + gastlistan[aldstaOchYngsta[0]][0] + ", " + gastlistan[aldstaOchYngsta[0]][1]);
        // [0]][0] hämtar förnamnet på den yngsta gästen, [0]][1]: Detta hämtar efternamnet på den yngsta gästen
        System.out.println();
    }

    public static void Addagast() {
        Scanner input2 = new Scanner(System.in);
        System.out.println("Adda ny gäst");
        int ledigaPlatser = gastlistan.length;
        for (int g = 0; g < gastlistan.length; g++) {
            if (gastlistan[g][0].equals("")) {
                System.out.println("Ange namn på den nya gästen");
                String nyGast = input2.nextLine();         // Skriv namn på den nya gästen och 

                System.out.println("Ange åldern på den nya gästen");
                String nyGastAlder = input2.nextLine();             // skriv ålder på den nya gästen

                gastlistan[g][0] = nyGast; // Här sparas namnet på den nya gästen
                gastlistan[g][1] = nyGastAlder; // Här sparas åldern på den nya gästen
                break;

            } else if (g == ledigaPlatser - 1) {   // den har gått igenom alla tillgängliga platser i arrayen. gästlistan är full 
                System.out.println("Det finns ingen ledig plats; den är full");
            }
        }
        printGastlista();
    }

    public static int[] AldstagastenOchYngstagasten() {
        int[] resultat = new int[2]; // Den här arrayen kommer att hålla indexen för den yngsta gästen (index 0) och den äldsta gästen (index 1).
        int Aldsta = 0; // håller den högsta åldern (gästtListan[0]<[1]);
        int Yngsta = 100; // håller den lägsta åldern(gästtListan[0][1]);
        for (int i = 0; i < gastlistan.length; i++) {
            if (!gastlistan[i][1].equals("")) { // Kontrollerar om åldern på gästen inte är en tom sträng; i så fall hoppar den till nästa if-sats.
                if (Integer.parseInt(gastlistan[i][1]) > Aldsta) { //Om åldern överstiger den nuvarande högsta åldern, uppdatera indexet för den äldsta gästen i resultatarrayen. 
                    Aldsta = Integer.parseInt(gastlistan[i][1]); // (Integer.parseInt) konvertera en sträng till en heltal
                    resultat[1] = i;
                } // Loopen kommer att köras så länge värdet av i är mindre än längden på arrayen gastlistan
                if (Integer.parseInt(gastlistan[i][1]) < Yngsta) { // Om åldern är lägre än den nuvarande lägsta åldern, uppdatera indexet för den yngsta gästen i resultatarrayen.
                    Yngsta = Integer.parseInt(gastlistan[i][1]);
                    resultat[0] = i;
                }
            }
        }
        return resultat; //  retunerar värderna
    }

    public static int[] VuxnaOchbarn() {
        int[] resultat = {0, 0};
        for (int R = 0; R < gastlistan.length ; R++) {
            if (gastlistan[R][0].equals("")) {
                continue;
            } else {
                int age = Integer.parseInt(gastlistan[R][1]);
                if (age <= 13) { 
                    resultat[0]++; // Då är det är ett barn
                } else {
                    resultat[1]++; // Då är det är ett vuxen
                }
            }
        }
        return resultat; 
    }

    public static void BytaAlderforGast() {
        System.out.println("Du valde att byta åldern på en gäst");
        
        printGastlista();
        
        Scanner input3 = new Scanner(System.in);
        int i = 0;
        while (i < gastlistan.length) {
            i++;
            System.out.println("Vilken gäst vill ändra sin ålder? Vänligen ange index");
            int index = input3.nextInt();
            input3.nextLine();
            System.out.println("Skriv vilken ålder du vill byta till:");
            String nyAlder = input3.nextLine();

            if (index < 0 || index >= gastlistan.length) {
                System.out.println("Det finns ingen gäst med det indexet");
            } else if (gastlistan[index][1].equals("")) { //  är en tom sträng
                System.out.println("Det finns ingen gäst i detta rum; det här rummet är tomt!");
            } else if (!gastlistan[index][1].equals("")) { // är rätt och åldern kommer att bytas
                gastlistan[index][1] = nyAlder;
            }

            System.out.println("Ålder är bytt");
            printGastlista();
            break;
        }
    }

    public static void BytaPlats() {
        System.out.println("Du valde att byta plats mellan index");

        boolean upptagenplats = true;
        int i = 0;
        while (i < gastlistan.length - 1) {
            i++;
        }
        if (gastlistan[i][0] != "") {
            upptagenplats = true;
        }
        if (upptagenplats) {
            Scanner byt = new Scanner(System.in);
            System.out.println("Ange numret på den första gäst som du vill byta plats för");
            int index1 = byt.nextInt();
            System.out.println("Ange numret på den andra gästen som du vill byta plats för");
            int index2 = byt.nextInt();
            if (index1 < 10 && index1 > -1 && index2 < 10 && index2 > -1) {
                String Namn; 
                String Age;
                Namn = gastlistan[index1][0];
                Age = gastlistan[index2][1];
                gastlistan[index1][0] = gastlistan[index2][0];
                gastlistan[index1][1] = gastlistan[index2][1];
                gastlistan[index2][0] = Namn;
                gastlistan[index2][1] = Age;
                System.out.println("Platsen är bytt");
                printGastlista();
            }
        }
    }

    public static void BytaNamnforGast() {
        System.out.println("Välja att Byta Namn för Gäst");
        printGastlista();
        
        Scanner input = new Scanner(System.in);
        
        System.out.println("vilken gäst vill byta namn? Vänligen ange index ");
        
        for (int j = 0; j < gastlistan.length; j++) {
            int index = input.nextInt();
            input.nextLine();
            

            if (index >= 0 && index < 10) {

                if (gastlistan[index][0].equals("")) { // kontrollerar om strängen är tom
                    System.out.println("det finns ingen gäst i det här rummet, det här rummet är tomt!");
                    break;
                }
            }
            if  (!gastlistan[index][0].equals("")) { //  kontrollerar om strängen inte är tom.
                System.out.println("Vad är det nya namnet på gästen?");
                String nyGastNamn = input.nextLine(); // Frågar användaren om det nya namnet
                gastlistan[index][0] = nyGastNamn;   // här sparas den nya namnet
                System.out.println("Namet är bytt");
                printGastlista();
                break;
            }
        }
    }

    public static void TabortGast() {
          System.out.println(" Du valde att Ta bort Gäst");
        boolean TabortGast = true;
        for (int a = 0; a < gastlistan.length; a++) {
            if (!gastlistan[a][0].equals("")) {
                TabortGast = true;
            }
        }
        if (TabortGast) {
            System.out.println("Vilken gäst vill du ta bort? Vänligen ange i vilken index");
            Scanner x = new Scanner(System.in);
            int index = x.nextInt();
            if (index < 0 || index >= gastlistan.length) { // Om inputen är mindre än 0 eller större än antal gästerna så ska den skriva så:
                System.out.println("Ogiltigt index");
            } else if (gastlistan[index][0].equals("")) {
                System.out.println("Finns ingen gäst här för att kunna ta bort");
            } else {
                System.out.println("Gästen :" + gastlistan[index][0] + " " + gastlistan[index][1] + " " + "Togs bort");
                
                gastlistan[index][0] = "";
                gastlistan[index][1] = "";
                printGastlista();
            }
        }
    }

    public static void main(String[] args) {
        Scanner x = new Scanner(System.in);
        boolean bio = true;
          do {
            printMenu();
            switch (x.next()) {
                case "1":
                    System.out.println("Välja för att visa gästlistan");
                    printGastlista();
                    break;
                case "2":
                    printStatistics();
                    break;
                case "3":
                    Addagast();
                    break;
                case "4":
                    BytaAlderforGast();
                    break;
                case "5":
                    BytaPlats();
                    break;
                case "6":
                    BytaNamnforGast();
                    break;
                case "7":
                    TabortGast();
                    break;
                case "-1":
                    System.out.println("Du valde att avbryta, Bye Tar hand om dig");
                    bio = false;
                    break;
            }
        } while (bio);
    }
}

