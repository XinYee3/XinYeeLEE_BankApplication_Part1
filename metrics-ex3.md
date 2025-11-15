Class : Bank
LOC : 393
WMC : 36
CBO : 4
LCOM : 0
Quick Notes : LCOM = 0 means it is extremely cohesive with all its methods work together on the class's data

Class : BankAccount (With modified method in Exercise 2)
LOC : 438
WMC : 39
CBO : 3
LCOM : 46
Quick Notes : LCOM = 46 is a red flag, suggesting it has more than one responsability

Class : Person
LOC : 294
WMC : 35
CBO : 1
LCOM : 79
Quick Notes : LCOM = 79 is considered normal for "getters/setters" which don't interact


Class with the highest WMC : BankAccount
Class with the highest CBO : Bank
Class worry about the most for future maintenance : BankAccount. It has a LCOM of 46, which means it has unrelated, complex methods (ex : withdrawMoney and loadFromText) in the same file. This means it violates the Single Responsibility Principle. It's trying to be a data object, a business logic handler and a file persistence handler all at once. A change to the file format could easily break the business logic (withdrawal), making it brittle and a future maintenance nightmare