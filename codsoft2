import java.util.Scanner;

class BankAccount {
    private double balance;

    public BankAccount(double initialBalance) {
        balance = initialBalance;
    }

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        balance += amount;
    }

    public boolean withdraw(double amount) {
        if (amount > balance) {
            return false;
        }
        balance -= amount;
        return true;
    }
}

class ATM {
    private BankAccount account;

    public ATM(BankAccount account) {
        this.account = account;
    }

    public void displayOptions() {
        System.out.println("1. Withdraw");
        System.out.println("2. Deposit");
        System.out.println("3. Check Balance");
        System.out.println("4. Exit");
    }

    public void processOption(int option) {
        Scanner scanner = new Scanner(System.in);

        switch (option) {
            case 1:
                System.out.print("Enter withdrawal amount: ");
                double withdrawAmount = scanner.nextDouble();
                if (account.withdraw(withdrawAmount)) {
                    System.out.println("Withdrawal successful. Remaining balance: " + account.getBalance());
                } else {
                    System.out.println("Insufficient funds.");
                }
                break;
            case 2:
                System.out.print("Enter deposit amount: ");
                double depositAmount = scanner.nextDouble();
                account.deposit(depositAmount);
                System.out.println("Deposit successful. New balance: " + account.getBalance());
                break;
            case 3:
                System.out.println("Your current balance is: " + account.getBalance());
                break;
            case 4:
                System.out.println("Thank you for using our ATM. Goodbye!");
                break;
            default:
                System.out.println("Invalid option. Please choose again.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        BankAccount userAccount = new BankAccount(1000.0);
        ATM atmMachine = new ATM(userAccount);
        Scanner scanner = new Scanner(System.in);

        int choice;

        do {
            atmMachine.displayOptions();
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();

            if (choice >= 1 && choice <= 4) {
                atmMachine.processOption(choice);
            } else {
                System.out.println("Invalid option. Please choose again.");
            }
        } while (choice != 4);
    }
}