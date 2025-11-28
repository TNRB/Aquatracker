# AquaTrack:
## A Smart Monitoring System for Household Water Usage


### -- ***Overview*** --
#### AquaTrack: A Smart Monitoring System for Household Water Usage is a console-based Java program designed to help households track and manage their daily water consumption. The system allows users to record water usage for various activities, view summaries, generate reports, and monitor overall consumption trends. Built using Object-Oriented Programming principles, AquaTrack applies encapsulation to protect and organize data within classes, ensuring controlled access through private fields and public methods. It uses inheritance to create a class hierarchy where general activity properties are stored in a base class, while specific activities such as bathing or laundry extend this class. Through polymorphism, the system enables different water-related activities to implement their own versions of usage calculations, allowing the same method call to behave differently depending on the object type. Abstraction is applied by defining abstract classes or interfaces that outline essential behaviors without revealing underlying code details, simplifying the structure and promoting reusability. Overall, AquaTrack provides an efficient, menu-driven console application that demonstrates proper OOP design while promoting responsible and informed water usage within the household.


### -- ***Concepts*** --
- __Encapsulation__ 
  - means wrapping data + methods inside a class and restricting access using access modifiers (like private).


        Example in code: private final double[] weeklyUsage = new double[4];
                 private final boolean[] entered = new boolean[4];

- __Inheritance__ 
  - means a class extends another class, inheriting its attributes and methods.

        Example in code: public abstract class BillCalculator
                 public class StandardBillCalculator extends BillCalculator

- __Polymorphism__ 
  - means the program can treat a subclass object as its superclass type and call the overridden methods properly.

        Example in code: private final BillCalculator calculator = new StandardBillCalculator();
		                               (Parent Class)                     (Child Class)
                 Method: calculator.computeBill(total)
		                  (Runtime Polymorphism)

- __Abstraction__ 
  - hides unnecessary complexity and provides a simplified interface.

        Example in code: public abstract class BillCalculator {
   	                     public abstract double computeBill(double totalUsage); }
    
  - Explanation: It forces subclasses to implement computeBill(). It hides implementation details (like VAT and environmental fee) exposes essential methods.


### ***-- Structure --***
The code structure of the project can be broken down into 6 classes. Each class fulfills a predefined role in the flow of the program. These are:

1. __AquaTrack__
- Serves as an entry point in the program, it begins the program loop by calling start().
- It then initializes the MenuController class.

2. __MenuController__
- Acts as the main interface of the program.
- Displays available actions and accepts user input.
- The menu options are as follows:
  - Budget-Based Calculator (budgetCalculator())
  - Set Monthly Limit (setLimit())
  - Input Weekly Usage (inputUsage())
  - View Usage History (viewHistory())
  - Estimate Water Bill (estimateBill())
  - Exit

3. __BillCalculator__
- It defines the framework for billing computations.
- It contains: 
  - Billing constants (rate, environmental fee %, VAT %).
  - A required method: public abstract double computeBill(double totalUsage);.
  - 2 Helper methods: computeEnvironmentalFee() and computeVAT().

4. __StandardBillCalculator__
- It performs the actual billing computations as needed by the program.
- Conducts a 4 step method:\
  - Utilizes the formula waterCharge = usage * RATE.
  - Add environmental fee.
  - Compute VAT on subtotal.
  - Return final bill.

5. __UsageRecord__
- It stores weekly usage via: double[] weeklyUsage = new double[4], then tracks which weeks have recorded data: boolean[] entered = new boolean[4]
- Based on the weekly usage, it then computes total usage.
- Prints history and compare to limit.

6. __LimitManager__
- It stores and returns the monthly limit.
- Computes a recommended weekly value.


### -- _How to Run_ --
The program can be run in a variety of ways, based on the requirements of the user. For example if the user intends to find out the recommended water usage for a set price point, then by typing 1 on the input screen they are able to input their budget and then it returns the recommended water usage limit in order to stick with the budget. If the user wishes to use the tracker, the steps to do so are as follows:
1. Set monthly limit
    -Choose option 2, then input the value recommended from the Budget-Based Calculator.

2. Input weekly recorded usage
   -Choose option 3, then choose the week number before inputting the recorded data.

3. View Usage History and Estimate Water Bill 
   -At any point the user may view the usage history and/or estimate their water bill by choosing the appropriate options.

### -- ***Sample Output*** --



