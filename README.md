Supermarket Management System
Welcome to the Supermarket Management System!

This Java program is designed to facilitate daily operations in a supermarket by managing products, recording sales, and calculating transactions.

Features:
Product Management :Add products with details such as name, price, and quantity.
Sales Recording: Record sales transactions and update product quantities accordingly.
Transaction Calculations: Calculate total price for purchases.
User-Friendly Interface: Easy navigation and interaction through command-line interface.

Usage:

Clone the Repository:
https://github.com/Subashkaruppaiah/Supermarket-Management-System-/commit/abc015799968c63f0f0ad971f4eee7b62ac8f974

Compile and Run:
cd supermarket-management-system
javac SupermarketManagementSystem.java
java SupermarketManagementSystem

Follow On-Screen Instructions: 
Enter the number of products, 
details for each product, 
and simulate a sale by entering the produc name and quantity.


Example// 

Add products to the supermarket
Supermarket supermarket = new Supermarket(numProducts);
supermarket.addProduct(new Product("Apple", 1.0, 50));
supermarket.addProduct(new Product("Banana", 0.5, 100));

// Display available products
supermarket.displayProducts();

// Simulate a sale
Product productToPurchase = supermarket.findProduct("Apple");
if (productToPurchase != null && productToPurchase.getQuantity() >= 10) {
    double totalPrice = productToPurchase.calculateTotalPrice(10);
    System.out.println("Total price: " + totalPrice);
    // Update inventory
    productToPurchase.setQuantity(productToPurchase.getQuantity() - 10);
} else {
    System.out.println("Product not found or insufficient quantity.");
}

Contributing:
Contributions are welcome!
Feel free to open an issue or submit a pull request for any improvements or additional features you'd like to see.
