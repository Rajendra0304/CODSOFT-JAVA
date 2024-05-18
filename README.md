# ********** ATM *********
# EXPLANATION
The provided Java code implements a simple ATM (Automated Teller Machine) interface using the Swing library for the graphical user interface (GUI). Here is a detailed explanation of the code:

### BankAccount Class
- **Purpose**: Represents a bank account with basic functionalities like checking the balance, depositing money, and withdrawing money.
- **Fields**:
  - `private double balance`: Stores the account balance.
- **Constructor**:
  - `public BankAccount(double balance)`: Initializes the account with a given balance.
- **Methods**:
  - `public double getBalance()`: Returns the current balance.
  - `public void deposit(double amount)`: Adds the specified amount to the balance.
  - `public boolean withdraw(double amount)`: Withdraws the specified amount if sufficient funds are available; returns true if successful, false otherwise.

### ATM Class
- **Inheritance**: Extends `JFrame` to create a main window for the ATM interface.
- **Constructor**:
  - `public ATM(BankAccount account)`: Sets up the GUI for the ATM.
    - **Window Settings**:
      - Sets the title of the window to "ATM".
      - Sets the window size to 400x300 pixels.
      - Specifies the default close operation (exit the application when the window is closed).
      - Centers the window on the screen.
    - **Components**:
      - Creates a `JPanel` and sets its layout to `GridLayout(4, 1)` for arranging buttons in a grid.
      - Creates four buttons: "Check Balance", "Deposit", "Withdraw", and "Exit".
      - Creates a `JLabel` to display the current balance.
    - **Button Actions**:
      - **Check Balance**:
        - Shows a message dialog displaying the current balance.
      - **Deposit**:
        - Prompts the user to enter a deposit amount.
        - Parses the input and, if valid, deposits the amount and updates the balance label.
        - Shows error messages for invalid input or negative amounts.
      - **Withdraw**:
        - Prompts the user to enter a withdrawal amount.
        - Parses the input and, if valid, attempts to withdraw the amount and updates the balance label.
        - Shows error messages for invalid input, negative amounts, or insufficient funds.
      - **Exit**:
        - Closes the application window.
    - **Layout**:
      - Adds the buttons to the panel.
      - Adds the panel to the center of the window and the balance label to the south.

### Main Method
- **Purpose**: Entry point of the application.
- **Functionality**:
  - Creates an instance of `BankAccount` with an initial balance of $1000.
  - Creates an instance of `ATM` and passes the bank account to it, thereby displaying the ATM interface.

### Summary
The code provides a basic ATM simulation where a user can:
- Check their balance.
- Deposit money into their account.
- Withdraw money from their account.
- Exit the application.

The interface is designed using Java Swing components, and it handles user input with basic validation and feedback through dialog boxes.
