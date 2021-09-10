#Problem 1
import java.util.Scanner;

public class BilPrima {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int bil, cek=0;
        
        System.out.println("PROGRAM JAVA MENENTUKAN BILANGAN PRIMA ATAU BUKAN");
        System.out.print("Masukan Angka : ");
        bil=input.nextInt();
   
        System.out.println("----------------------------------------------");
        for (int i=2; i<=bil; i++){
            if (bil%i==0){
                cek++;
            } 
        }
        
        if (cek==1){
            System.out.println(bil+" adalah bilangan prima");
        }else {
            System.out.println(bil+" bukan bilangan prima");
        }  
    }
    
}

#Problem 2
import java.util.Scanner;

public class EvenOOD {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("Masukkan Sebuah angka : ");
        int angka = input.nextInt();

        if(angka % 2 == 0){
            System.out.println("Angka"+angka+" adalah bilangan genap");
        }else{
            System.out.println("Angka"+angka+" adalah bilangan ganjil");
        }
    }
    
}

#problem 3
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Arrays;

public class BinarySearch {

    public static void main(String[] args) {
        BufferedReader input = new BufferedReader(new InputStreamReader(System.in));
        try {
            System.out.print("Masukkan angka : ");
            int index = 0;
            int number = Integer.parseInt(input.readLine());
            int[] binary = { 11, 2, 7, 1, 3, 32, 39, 66, 46, 28, 90, 88 };
            int binaryLen = binary.length; // len(array)
            for (int x : binary) { // for x in array
                if (number == x) {
                    System.out.println("Angka ditemukan pada index ke-" + index);
                    break;
                }
                index++;
            }
            if (index == binaryLen) {
                System.out.println("Angka tidak ditemukan");
            }
        } catch (IOException exception) {
            System.out.println("Input Error!");
        }
    }
    
}

#Problem 4
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Arrays;

public class KnightAndDragon {

    public static void main(String[] args) throws IOException {
        BufferedReader input = new BufferedReader(new InputStreamReader(System.in));
        System.out.print("Input jumlahDragon : ");
        int numberin = Integer.parseInt(input.readLine());
        int[] dragon = new int[numberin];
        for( int i = 0; i < dragon.length; i++ ){
            int x = i+1;
            System.out.print("dragon" + x + ": ");
            dragon[i] = Integer.parseInt(input.readLine());
        }
        System.out.print("Input jumlah Knight : ");
        int number = Integer.parseInt(input.readLine());
        int Knight[] = new int[number];
        for( int i = 0; i < Knight.length; i++ ){
            int y = i+1;
            System.out.print("Knight" + y + ": ");
            Knight[i] = Integer.parseInt(input.readLine());
        }
        Arrays.sort(Knight);
        Arrays.sort(dragon);
        int indeksDragon = 0;
        int power = 0;
        for (int x : Knight) {
            if (indeksDragon < dragon.length) {
                if (x >= dragon[indeksDragon]) { // dragon[1]
                    power += x;
                    indeksDragon++;
                }
            }
        }
        System.out.println("---------------------------");
        if (indeksDragon == dragon.length) { // len(dragon)
            System.out.println(power);
        } else {
            System.out.println("Knight Fall");
        }
    }
    
}
