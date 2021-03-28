public class ToolStore extends NormalLocation{
    ToolStore(Player player){

        super(player," Magaza ");

    }

    public boolean getLocation(){
        System.out.println(" Mevcut Paraniz : " + player.getMoney());
        System.out.println("1. Silahlar ");
        System.out.println("2. Zirhlar ");
        System.out.println("3. Cikis ");
        System.out.println("Seciminiz : ");
        int selTool = scan.nextInt();
        switch(selTool){

            case 1 :
                int selItemID= weaponMenu();
                buyWeapon(selItemID);
                break;
            case 2:
            selItemID = armorMenu();
            buyArmor(selItemID);
                break;
            default:
                break;
        }
        return true;

    }
    public int armorMenu(){

        System.out.println("1. Hafif \t < Para : 15 - Hasar : 1 >");
        System.out.println("2. Orta \t < Para : 25 - Hasar : 3 >");
        System.out.println("3. Agir \t < Para : 40 - Hasar : 5 >");
        System.out.println("4. Cikis");
        System.out.println("Silah seciniz : ");
        int selArmorID = scan.nextInt();
        return selArmorID;


    }
    public void buyArmor(int itemID) {

        int avoid = 0, price = 0;
        String aName = null;
        switch (itemID) {

            case 1:
                avoid = 1;
                aName = "Hafif Zirh";
                price = 15;
                break;
            case 2:
                avoid = 3;
                aName = "Orta Zirh";
                price = 15;
                break;
            case 3:
                avoid = 5;
                aName = "Agir Zirh";
                price = 40;
            case 4:
                System.out.println("Cikis Yapiliyor ");
            default:
                System.out.println("Gecersiz islem");
                break;
        }
        if (price > 0) {

            if (player.getMoney() >= price) {
                player.getInv().setArmor(avoid);
                player.getInv().setaName(aName);
                player.setMoney(player.getMoney() - price);
                System.out.println(aName + "  satin aldiniz Engellenen Hasar : "+ player.getInv().getArmor());
                System.out.println(" Kalan Para : " + player.getMoney());
            } else {

                System.out.println("Bakiye Yetersiz.!");
            }

        }
    }
    public int weaponMenu(){

        System.out.println("1. Tabanca \t < Para : 25 - Hasar : 2 >");
        System.out.println("2. Kilic \t < Para : 35 - Hasar : 3 >");
        System.out.println("3. Tufek \t < Para : 45 - Hasar : 7 >");
        System.out.println("4. Cikis");
        System.out.println("Silah seciniz : ");
        int selWeaponID= scan.nextInt();
        return selWeaponID;
    }

    public void buyWeapon(int itemID){
        int damage= 0,price = 0;
        String wName=null;
        switch (itemID){

            case 1:
                damage = 2;
                wName ="Tabanca";
                price = 25;
                break;
            case 2:
                damage = 3;
                wName ="Kilic";
                price = 35;
                break;
            case 3 :
                damage = 7;
                wName ="Tufek";
                price = 45;
            case 4 :
                System.out.println("Cikis Yapiliyor ");
            default:
                System.out.println("Gecersiz islem");
                break;
        }

        if(price > 0){

            if(player.getMoney() >= price ) {
                player.getInv().setDamage(damage);
                player.getInv().setwName(wName);
                player.setMoney(player.getMoney()-price);
                System.out.print(wName + "  satin aldiniz , Onceki Hasar : "+player.getDamage() + ",Yeni Hasar : " + player.getTotalDamage() );
                System.out.println(" Kalan Para : " + player.getMoney());
            }
            else{

                System.out.println("Bakiye Yetersiz.!");
            }
        }


        }
    }


