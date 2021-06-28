//Say for instance we are taking up Burgers as an example for the understanding. 
//We will create three classes named as Hamburger, DeluxeBurger, HealthyBurger.
//DB & HB are inherited classes from the Hamburger class will have feilds, constructors, methods etc.

//Hamburger.java
public class Hamburger {
  private String name;
    private String meat;
    private double price;
    private String breadRollType;

    public Hamburger(String name, String meat, double price, String breadRollType) {
        this.name = name;
        this.meat = meat;
        this.price = price;
        this.breadRollType = breadRollType;
    }

    private String addition1Name;
    private double addition1Price;

    private String addition2Name;
    private double addition2Price;

    private String addition3Name;
    private double addition3Price;

    private String addition4Name;
    private double addition4Price;

    public void addHamburgerAddition1(String name, double price) {
        this.addition1Name = name;
        this.addition1Price = price;
    }

    public void addHamburgerAddition2(String name, double price) {
        this.addition2Name = name;
        this.addition2Price = price;
    }

    public void addHamburgerAddition3(String name, double price) {
        this.addition3Name = name;
        this.addition3Price = price;
    }

    public void addHamburgerAddition4(String name, double price) {
        this.addition4Name = name;
        this.addition4Price = price;
    }

    public double itemizeHamburger() {
        double hamburgerTotalPrice = this.price;

        if (addition1Name != null) {
            hamburgerTotalPrice += this.addition1Price;
            System.out.println("Additional added " + addition1Name + " for an extra price of " + addition1Price);
        }

        if (addition2Name != null) {
            hamburgerTotalPrice += this.addition2Price;
            System.out.println("Additional added " + addition2Name + " for an extra price of " + addition2Price);
        }

        if (addition3Name != null) {
            hamburgerTotalPrice += this.addition3Price;
            System.out.println("Additional added " + addition3Name + " for an extra price of " + addition3Price);
        }

        if (addition4Name != null) {
            hamburgerTotalPrice += this.addition4Price;
            System.out.println("Additional added " + addition4Name + " for an extra price of " + addition4Price);
        }
        return hamburgerTotalPrice;
    }
}


//DeluxeBurger.java

public class DeluxeBurger extends Hamburger {
    public DeluxeBurger() {
        super("Deluxe", "Sausage & Bacon", 14.54, "White");
        super.addHamburgerAddition1("Chips", 2.75);
        super.addHamburgerAddition2("Drink", 1.81);
    }

    @Override
    public void addHamburgerAddition1(String name, double price) {
        System.out.println("Cannot not add additional items to a deluxe burger");
    }

    @Override
    public void addHamburgerAddition2(String name, double price) {
        System.out.println("Cannot not add additional items to a deluxe burger");
    }

    @Override
    public void addHamburgerAddition3(String name, double price) {
        System.out.println("Cannot not add additional items to a deluxe burger");
    }

    @Override
    public void addHamburgerAddition4(String name, double price) {
        System.out.println("Cannot not add additional items to a deluxe burger");
    }

}

//HealthyBurger.java 

public class HealthyBurger extends Hamburger {
    private String healthyExtra1Name;
    private double healthyExtra1Price;
    private String healthyExtra2Name;
    private double healthyExtra2Price;
    public HealthyBurger(String meat, double price) {
        super("Healthy burger", meat, price, "Brown rye");
    }
    public void addHealthyAddition1(String name, double price){
        this.healthyExtra1Name = name;
        this.healthyExtra1Price = price;
        System.out.println("Added " + this.healthyExtra1Name + " for an extra "
                + this.healthyExtra1Price);
    }
    public void addHealthyAddition2(String name, double price){
        this.healthyExtra2Name = name;
        this.healthyExtra2Price = price;
        System.out.println("Added " + this.healthyExtra2Name + " for an extra "
                + this.healthyExtra2Price);
    }
    
    @Override
    public double itemizeHamburger() {
 
        return this.healthyExtra1Price + this.healthyExtra2Price + super.itemizeHamburger();
    }
}

