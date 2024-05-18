# ATM 
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

# NumberGame
The provided Java code implements a number guessing game using the Swing library for the graphical user interface (GUI). Here is a detailed explanation of the code:

### Class Structure and Initialization

**Class Definition and Interface Implementation**:
- `public class NumberGame extends JFrame implements ActionListener`:
  - Extends `JFrame` to create a main window for the game.
  - Implements `ActionListener` to handle button click events.

**Constants and Fields**:
- `private final int minRange = 1;` and `private final int maxRange = 100;`:
  - Define the range within which the random number will be generated.
- `private final int attemptsLimit = 5;`:
  - Defines the maximum number of attempts a player has to guess the number.
- `private int randomNumber;`:
  - Stores the randomly generated number that the player has to guess.
- `private int attempts;`:
  - Keeps track of the number of attempts made by the player.
- `private boolean guessedCorrectly;`:
  - Indicates whether the player has guessed the number correctly.

**GUI Components**:
- `private JLabel titleLabel, messageLabel, attemptsLabel;`:
  - Labels for displaying the title, messages to the player, and the number of attempts.
- `private JTextField guessField;`:
  - Text field for the player to enter their guess.
- `private JButton guessButton, newGameButton;`:
  - Buttons for submitting a guess and starting a new game.

### Constructor and GUI Setup

**Constructor**:
- `public NumberGame()`:
  - Sets the title of the window to "Number Guessing Game".
  - Initializes all the GUI components.
  - Adds action listeners to the buttons.
  - Uses a `GridBagLayout` for flexible and complex component layout.
  - Adds components to the panel with appropriate layout constraints.
  - Calls `startGame()` to initialize the game state.

### Game Initialization and State Management

**startGame Method**:
- `private void startGame()`:
  - Generates a random number within the specified range.
  - Resets the number of attempts and the guessed correctly flag.
  - Updates the message and attempts labels.
  - Enables the guess input field and guess button.

**updateMessage Method**:
- `private void updateMessage()`:
  - Updates the `messageLabel` based on whether the number has been guessed correctly.

**updateAttemptsLabel Method**:
- `private void updateAttemptsLabel()`:
  - Updates the `attemptsLabel` to reflect the current number of attempts made.

### Event Handling

**actionPerformed Method**:
- `public void actionPerformed(ActionEvent e)`:
  - Handles button clicks for `guessButton` and `newGameButton`.
  - **Guess Button**:
    - Checks if the game is still ongoing.
    - Tries to parse the user’s guess from the text field.
    - Increments the attempt count and updates the attempts label.
    - Checks if the guess is correct, too low, or too high, and updates the message accordingly.
    - Disables the input field and guess button if the number is guessed correctly or if the attempts limit is reached.
    - Shows an error message if the input is invalid.
  - **New Game Button**:
    - Calls `startGame()` to reset the game.

### Main Method

**Main Method**:
- `public static void main(String[] args)`:
  - Creates an instance of `NumberGame` to start the game.

### Summary
This code sets up a simple number guessing game where the player has to guess a randomly generated number between 1 and 100. The player has up to 5 attempts to guess the number correctly. The game provides feedback after each guess and allows the player to start a new game after either winning or using up all attempts. The GUI components and event handling are managed using Java Swing, providing a graphical interface for the game.

# StudentGrade
The provided Java code implements a Student Grade Calculator using the Swing library for the graphical user interface (GUI). Below is a detailed explanation of the code:

### Class Structure and Initialization

**Class Definition**:
- `public class StudentGrade extends JFrame`:
  - Extends `JFrame` to create a main window for the application.

### GUI Components and Layout

**Fields**:
- `private JLabel totalMarksLabel;`: Label to display the total marks.
- `private JLabel averagePercentageLabel;`: Label to display the average percentage.
- `private JLabel gradeLabel;`: Label to display the grade.
- `private JTextField numSubjectsField;`: Text field to enter the number of subjects.
- `private JButton calculateButton;`: Button to trigger the grade calculation.

**Constructor**:
- `public StudentGrade()`:
  - Sets the title of the window to "Student Grade Calculator".
  - Sets the window size to 400x200 pixels.
  - Sets the default close operation to exit the application when the window is closed.
  - Centers the window on the screen.
  - Initializes and sets up the layout of GUI components using `GridBagLayout`.
  - Adds action listener to the `calculateButton` to handle button click events.

**Layout Details**:
- A `JPanel` with `GridBagLayout` is used to organize the components.
- `GridBagConstraints` are used to specify the position and layout behavior of each component.
- Labels and text fields are added to the panel with appropriate constraints to create a user-friendly interface.

### Event Handling

**Action Listener**:
- `calculateButton.addActionListener(new ActionListener() {...})`:
  - An anonymous inner class implements the `ActionListener` interface.
  - The `actionPerformed` method calls the `calculateGrade()` method when the button is clicked.

### Grade Calculation Logic

**calculateGrade Method**:
- `private void calculateGrade()`:
  - Reads the number of subjects from `numSubjectsField`.
  - Initializes `totalMarks` to 0.
  - Uses a for-loop to prompt the user to enter marks for each subject using `JOptionPane.showInputDialog`.
  - Validates the entered marks to ensure they are between 0 and 100.
  - Accumulates the total marks.
  - Calculates the average percentage.
  - Calls `calculateGrade(averagePercentage)` to determine the grade based on the average percentage.
  - Updates the labels (`totalMarksLabel`, `averagePercentageLabel`, `gradeLabel`) with the calculated values.
  - Catches `NumberFormatException` to handle invalid input for the number of subjects and displays an error message.

**calculateGrade Method** (Overloaded):
- `private String calculateGrade(double averagePercentage)`:
  - Determines the grade based on the average percentage using conditional statements.
  - Returns the corresponding grade as a string:
    - `A` for 90% and above.
    - `B` for 80% and above.
    - `C` for 70% and above.
    - `D` for 60% and above.
    - `E` for 40% and above.
    - `F` for below 40%.

### Main Method

**Main Method**:
- `public static void main(String[] args)`:
  - Uses `SwingUtilities.invokeLater` to ensure that the GUI creation and updates are done on the Event Dispatch Thread.
  - Creates an instance of `StudentGrade` to start the application.

### Summary
This code creates a simple GUI application to calculate and display the total marks, average percentage, and grade for a student based on marks entered for multiple subjects. The GUI includes input fields for the number of subjects, buttons to trigger calculations, and labels to display results. The application validates user input, performs necessary calculations, and updates the GUI with results, providing a user-friendly experience.
