public class MiniATM {
    public static void main(String[] args) {
        User user = new User("Nambi Rajan", 10467780004, 1408, 30000.0);

        ATM atm = new ATM();

        boolean authenticated = atm.authenticateUser(user.getAccountNumber(), user.getPin());

        if (authenticated) {
            System.out.println("Welcome, " + user.getName() + "!");
            double balance = atm.checkBalance();
            System.out.println("Your account balance: $" + balance);

            double withdrawalAmount = 100.0;
            atm.withdraw(withdrawalAmount);
            
            balance = atm.checkBalance();
            System.out.println("Withdrawn: $" + withdrawalAmount);
            System.out.println("Updated balance: $" + balance);
        } else {
            System.out.println("Authentication failed. Please check your account number and PIN.");
        }
    }
}

