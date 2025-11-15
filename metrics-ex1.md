Class : Bank
LOC (approx) : 393
NOM : 14
Short description of responsibility : Manages the collection of BankAccount objects (add, find, delete). Calculates aggregate data (avg/min/max balance). Handles saving all accounts to a file.
Size roughly matches its responsibility : Yes, around 28 lines per method (393/14)

Class : BankAccount
LOC (approx) : 405
NOM : 20
Short description of responsibility : Represents a single bank account. Holds data (holder, balance, limit) and business logic (deposit, withdraw). Also contains logic for loading/coverting a single account from/to text.
Size roughly matches its responsibility : Yes, around 20 lines per method (405/20)

Class : Person
LOC (approx) : 294
NOM : 23
Short description of responsibility : A data class that holds all the information for a single person (name, age, gender, etc.). Contains multiple constructors, getters, setters and validation logic.
Size roughly matches its responsibility : Yes, around 13 lines per method (294/23)

Class : BankAccountApp
LOC (approx) : 447
NOM : 2
Short description of responsibility : The main application driver, contains the main method which handles all console I/O, user menus and application flow.
Size roughly matches its responsibility : No, around 224 lines per method (447/2)