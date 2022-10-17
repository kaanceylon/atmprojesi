# atmprojesi
atm projesi
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        String userName, password;
        Scanner input = new Scanner(System.in);

        int right = 3;
        int select;
        int price;
        int balance = 1500;


        while (right > 0) {
            System.out.print("Kullanıcı adınızı giriniz : ");
            userName = input.nextLine();

            System.out.print("Şifrenizi giriniz : ");
            password = input.nextLine();
            if (userName.equals("Kaan") && password.equals("kaan123")) {
                System.out.print("Hoşgeldin Kaan! ");
                do {
                    System.out.print("1- Para Yatırma\n" +
                            "2- Para Çekme\n" +
                            "3- Bakiye Sorgulama\n" +
                            "4- Çıkış yap");
                    System.out.print("Lütfen yapmak istediğiniz işlemi seçin : ");
                    select = input.nextInt();
                    switch (select) {
                        case 1:
                            System.out.print("Yatırılacak para miktarını giriniz : ");
                            price = input.nextInt();
                            balance += price;
                            break;
                        case 2:
                            System.out.print("Çekilecek para miktarı : ");
                            price = input.nextInt();
                            if (price > balance) {
                                System.out.print("Bakiyeniz yetersiz!! ");
                            } else {
                                balance -= price;
                            }
                            break;
                        case 3:
                            System.out.print("Bakiyeniz : " + balance);
                            break;
                        case 4:
                            System.out.print("Görüşmek üzere : ");
                        default:
                            System.out.print("Lütfen 1 ile 4 arasında bir seçim yapın! ");
                    }
                } while (select != 4);
            } else {
                right--;
                System.out.print("Hatalı kullanıcı adınız şifre! ");
                if (right == 0) {
                    System.out.print("Hesabınız bloke olmuştur. ");


                } else {
                    System.out.println("Tekrar deneyiniz.. Kalan hakkınız : " + right);

                }

            }
        }
    }
}
































