import java.util.Scanner;

public class SupermarketManagementSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to Supermarket Management System!");

        System.out.print("Enter number of products: ");
        int numProducts = scanner.nextInt();
        Supermarket supermarket = new Supermarket(numProducts);

        for (int i = 0; i < numProducts; i++) {
            System.out.println("\nEnter details for product " + (i + 1) + ":");
            System.out.print("Name: ");
            String name = scanner.next();
            System.out.print("Price: ");
            double price = scanner.nextDouble();
            System.out.print("Quantity: ");
            int quantity = scanner.nextInt();

            supermarket.addProduct(new Product(name, price, quantity));
        }

        // Display available products
        supermarket.displayProducts();

        // Simulate a sale
        System.out.println("\nEnter product name to purchase: ");
        String productName = scanner.next();
        System.out.println("Enter quantity: ");
        int quantityToPurchase = scanner.nextInt();

        Product productToPurchase = supermarket.findProduct(productName);
        if (productToPurchase != null && productToPurchase.getQuantity() >= quantityToPurchase) {
            double totalPrice = productToPurchase.calculateTotalPrice(quantityToPurchase);
            System.out.println("Total price: " + totalPrice);
            // Update inventory
            productToPurchase.setQuantity(productToPurchase.getQuantity() - quantityToPurchase);
        } else {
            System.out.println("Product not found or insufficient quantity.");
        }

        scanner.close();
    }
}

class Product {
    private String name;
    private double price;
    private int quantity;

    public Product(String name, double price, int quantity) {
        this.name = name;
        this.price = price;
        this.quantity = quantity;
    }

    // Getters and setters
    public double calculateTotalPrice(int quantity) {
        return price * quantity;
    }

    public String getName() {
        return name;
    }

    public int getQuantity() {
        return quantity;
    }

    public double getPrice() {
        return price;
    }

    public void setName(String name) {
        this.name = name;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }
}

class Supermarket {
    private Product[] products;
    private int numProducts;

    public Supermarket(int size) {
        products = new Product[size];
        numProducts = 0;
    }

    public void addProduct(Product product) {
        products[numProducts++] = product;
    }

    public void displayProducts() {
        System.out.println("\nProduct list:");
        for (int i = 0; i < numProducts; i++) {
            Product product = products[i];
            System.out.println("Name: " + product.getName() + ", Price: " + product.getPrice() + ", Quantity: " + product.getQuantity());
        }
    }

    public Product findProduct(String productName) {
        for (int i = 0; i < numProducts; i++) {
            if (products[i].getName().equalsIgnoreCase(productName)) {
                return products[i];
            }
        }
        return null;
    }
}
