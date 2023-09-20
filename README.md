import java.util.Scanner;
class OnlineReservation{
    private static boolean[] seats = new boolean[10];

    public static void main(String[] args){
        Scanner scanner = new Scanner(System.in);
        while (true){
            System.out.println("\nplease select an option:");
            System.out.println("1. view seat map");
            System.out.println("2. Reserve seat");
            System.out.println("3. Cancel Reservation");
            System.out.println("4. Exit");

            int option = scanner.nextInt();

            switch (option){
                case 1:
                    ViewSeatMap();
                    break;
                case 2:
                    reservedseat();
                    break;
                case 3:
                    CancelReservation();
                    break;
                case 4:
                    System.out.println(0);
                default:
                    System.out.println("Invalid option");
            }
        }
    }
    private static void ViewSeatMap() {
        System.out.println("\nCurrent seat Map");
        for (int i = 0; i < seats.length; i++) {
            if (seats[i]) {
                System.out.print("X ");
            } else {
                System.out.print((i + 1) + " ");
            }
        }
        System.out.println();
    }
     private static void reservedseat() {
         Scanner scanner = new Scanner(System.in);
         System.out.print("\nEnter seat number (1-10): ");
         int seatNumber = scanner.nextInt();
         if (seatNumber < 1 || seatNumber > 10) {
             System.out.println("Invalid seat number");
         } else if (seats[seatNumber - 1]) {
             System.out.println("seat already reserved!");
         } else {
             seats[seatNumber - 1] = true;
             System.out.println("seat reserved!");
         }
     }
     private static void CancelReservation(){
         Scanner scanner = new Scanner(System.in);
         System.out.println("\nEnter seat number (1-10) : ");
         int seatNumber = scanner.nextInt();
         if(seatNumber < 1 || seatNumber >10){
             System.out.println("Invalid seat number");
         }else if(!seats[seatNumber-1]){
             System.out.println("seat not reserved!");
         }else{
             seats[seatNumber -1 ]=false;
             System.out.println("Reservation Canceled! ");
         }
     }
}
