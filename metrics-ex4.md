Issue 1
Rule name : Null pointers should not be dereferenced (java:S2259)
File and line : BankAccount.java:173
Explanation : This is a critical bug. The code initializes fileScanner to null (line 171) and then immediately tries to use it in the while loop (line 173) before it's ever assigned. This will cause a NullPointerException everytime loadFromText is called.

Issue 2
Rule name : Try-with-resources should be used (java:S2093)
File and line : BankAccount.java:172
Explanation : This is a major code smell and potential bug. The code is manually managing file streams (fis) in a complex try-finally block. This is error-prone (ex : if fis.close() throws an error, fileScanner.close() is never called), which can lead to resource leaks.

Issue 3
Rule name : Private fields only used as local variables in methods should become local variables (java:S1450)
File and line : BankAccount.java:22
Explanation : This is a good 'code smell' catch. The success field isn't actually part of the BankAccount's state. It's just being used as a temporary variable inside the withdrawMoney method. This is misleading and should just be a local variable.


I have fixed the first two issues (S2259, S2093). After re-run SonarQube these two issues disappeared.

Yes, SonarQube issues appear more often in the classes with higher WMC. The CK Metrics analysis showed that BankAccount had the highest WMC (39) and a high LCOM (46). This means that the class was complex and not cohesive. The class is trying to do file I/O (loadFromText) in addition to its business logic (withdrawMoney). This lack of cohesion (high LCOM) and high complexity (high WMC) led directly to the critical bugs SonarQube found, like the NullPointerException and the resource leaks.