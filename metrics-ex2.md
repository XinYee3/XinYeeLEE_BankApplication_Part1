Choosen method : public boolean withdrawMoney(double arg0)
Cyclomatic complexity value : 5

Code :
// CC decision point 1 : if
// CC decision point 2 : first &&
// CC decision point 3 : second &&
// CC decision point 4 : third &&
public boolean withdrawMoney(double var1) {
      if (var1 >= 0.0 && this.balance >= var1 && var1 < this.withdrawLimit && var1 + this.amountWithdrawn <= this.withdrawLimit) {
         this.balance -= var1;
         this.success = true;
         this.amountWithdrawn += var1;
      } else {
         this.success = false;
      }

      return this.success;
}

Refactoring proposal : Extracting the entire boolean condition into a new, private helper method. This helper method, named canWithdraw(double amount), would perform and document these four checks. This will make the withdrawMoney method much simpler and its logic far more self-explanatory.

Cyclomatic complexity value after refactoring : 2 (I have modified the original method and create the helper method in the BankAccount.java)