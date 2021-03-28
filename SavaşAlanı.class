import java.util.Locale;

public abstract class BattleLoc extends Location{

    protected Obstacle obstacle;
    protected String award;
    BattleLoc(Player player, String name , Obstacle obstacle,String award) {

        super(player);
        this.name = name;
        this.obstacle = obstacle;
        this.award = award;
    }

    public boolean getLocation(){
        int obsCount = obstacle.count();
        System.out.println("Suan Buradasiniz : "+ this.getName() );
        System.out.println("Dikkatli ol ! Burada " + obsCount + " tane " + obstacle.getName()+" Yasiyor");
        System.out.print("<S>avas veya <K>ac");
        String selCase = scan.nextLine();
        selCase = selCase.toUpperCase();
        if(selCase.equals("S")){
            if(combat(obsCount)){

                System.out.println(this.getName()+" Bolgesindeki Tum dusmanlari temizlediniz ! ");
                if(this.award.equals("Yemek") && player.getInv().isFood() == false){

                    System.out.println(this.award + " Kazandiniz ! ");
                    player.getInv().setFood(true);

                }

                else if (this.award.equals("Su") && player.getInv().isWater() == false){
                    System.out.println(this.award + " Kazandiniz ! ");
                    player.getInv().setWater(true);

                }

                else if((this.award.equals("Yanacak Odun") && player.getInv().isFirewood() == false)){

                    System.out.println(this.award + " Kazandiniz ");
                    player.getInv().setFirewood(true);
                }

                return true;

            }

            if(player.getHealthy() <= 0){

                System.out.println(" Oldunuz ! ");
                return false;
            }

        }

        else{

            System.out.println(" Yara almadan basariyla kactiniz ! ");
        }

        return true;
    }

    public boolean combat(int obsCount){
        for(int i = 0; i< obsCount;i++){
            int defObsHealth = obstacle.getHealth();

            playerStats();
            enemyStats();
            while(player.getHealthy() > 0 && obstacle.getHealth() > 0 ){

                System.out.print(" <V>ur veya <K>ac");
                String selCase = scan.nextLine();
                selCase = selCase.toUpperCase();
                if(selCase.equals("V") ){
                    System.out.println("Siz vurdunuz ! ");
                    obstacle.setHealth(obstacle.getHealth()-player.getTotalDamage());
                    afterHit();
                    if(obstacle.getHealth() > 0){
                        System.out.println();
                        System.out.println(obstacle.getName()+" size vurdu ! ");
                        player.setHealthy(player.getHealthy()-(obstacle.getDamage()-player.getInv().getArmor()));
                        afterHit();

                    }



                }
                else{
                    return false;
                }
            }
            if(obstacle.getHealth() < player.getHealthy()){

                System.out.println("Dusmani yendiniz ! ");
                player.setMoney(player.getMoney()+obstacle.getAward());
                System.out.println("Guncel paraniz : " + player.getMoney());
                obstacle.setHealth(defObsHealth);


            }

            else{
                return false;
            }
            System.out.println("--------------");
        }
        return true;
    }

    public void playerStats(){

        System.out.println("Oyuncu Bilgileri \n-----------");
        System.out.println("Can : "+ player.getHealthy());
        System.out.println("Hasar : "+ player.getTotalDamage());
        System.out.println("Para : " + player.getMoney());
        if(player.getInv().getDamage() > 0 ){

            System.out.println("Silah : " + player.getInv().getwName() );
        }
        if(player.getInv().getArmor() > 0 ) {

            System.out.println("Zirh : " + player.getInv().getaName());
        }

    }

    public void enemyStats(){

        System.out.println("\n"+obstacle.getName() + " Degerleri \n------------");
        System.out.println("Can : "+ obstacle.getHealth());
        System.out.println("Hasar : "+ obstacle.getDamage());
        System.out.println("Odul : "+obstacle.getAward());

    }

    public void afterHit(){

        System.out.println(" Oyuncu cani : " + player.getHealthy());
        System.out.println(obstacle.getName()+"Cani : " + obstacle.getHealth());
        System.out.println();

    }


}
