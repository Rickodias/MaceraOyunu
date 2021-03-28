import javax.tools.Tool;
import java.util.Scanner;

public class Game {

    Player player;
    Location location;
    Scanner scan = new Scanner (System.in);


    public void login(){

        Scanner scan = new Scanner(System.in);
        System.out.println("Macera oyununa hosgeldiniz !");
        System.out.println("Oyuna baslamadan once isminizi giriniz !");
        //String playerName=scan.nextLine();
        player = new Player("a");
        player.selectCha();
        start();

    }
    public void start() {

        while(true){

            System.out.println();
            System.out.println("========================");
            System.out.println();
            System.out.println("Eylem gerceklestirmek icin bir yer seciniz:");
            System.out.println("1.Guvenli Ev ---> Size ait guvenli bir mekan,dusman yok! ");
            System.out.println("2.Magara ---> Karsiniza belki zombi cikabilir! ");
            System.out.println("3.Orman ---> Karsiniza belki vampir cikabilir !");
            System.out.println("4.Nehir ---> Karsiniza belki ayi cikabilir !");
            System.out.println("5.Magaza ---> Silah veya zirh alabilirsiniz !");
            System.out.print("Gitmek istediginiz yer : ");

            int selLoc = scan.nextInt();
            while ( selLoc < 0 || selLoc > 5 ){

                System.out.print("Lutfen gecerli bir yer seciniz : ");
                selLoc = scan.nextInt();
            }

            switch (selLoc){

                case 1:
                    location= new SafeHouse(player);
                    break;
                case 2 :
                    location = new Cave(player);
                    break;
                case 3 :
                    location = new Forest(player);
                    break;
                case 4 :
                    location = new River(player);
                    break;
                case 5 :
                    location = new ToolStore(player);
                    break;


                default:
                    location = new SafeHouse(player);
            }
            if(location.getClass().getName().equals("SafeHouse")){
                if(player.getInv().isFirewood() && player.getInv().isFood() && player.getInv().isWater())
                {

                    System.out.println(" Tebrikler Oyunu Kazandiniz !  ");
                    break;
                }

            }
            if(!location.getLocation()){
                System.out.println("Oyun bitti ");
                break;
            }
        }
    }
}
