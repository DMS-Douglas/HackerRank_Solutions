# Douglas Souza
# Hacker Rank - 30 Days of Code Challenges - Submissions (Medium/Hard)

[![Hacker Rank Logo](https://hrcdn.net/hackerrank/assets/brand/h_mark_sm-9c05999c62674028552f4e813728e591.svg)](https://www.hackerrank.com/douglas15) - [![Golden Badges](../badges.png)](https://www.hackerrank.com/douglas15)


Day 0: Hello, World. (https://www.hackerrank.com/challenges/30-hello-world/problem)

```java
function processData(inputString) {
    // This line of code prints the first line of output
    console.log("Hello, World.");
    
    // Write the second line of output that prints the contents of 'inputString' here.
    console.log(inputString);
}
```


Day 1: Data Types (https://www.hackerrank.com/challenges/30-data-types/problem)

```java
        int secondI = scan.nextInt();

        double secondD = scan.nextDouble();

        scan.nextLine();
        String secondS = scan.nextLine();

        System.out.println(secondI + i);
        System.out.println(secondD + d);
        System.out.println(s + secondS);
```


Day 2: Operators (https://www.hackerrank.com/challenges/30-operators/problem)

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    // Complete the solve function below.
    static void solve(double meal_cost, int tip_percent, int tax_percent) {

        //meal_cost = 10.25;
        //tip_percent = 17;
        //tax_percent=5;
        
        MathContext mathContext = new MathContext(6, RoundingMode.HALF_EVEN);
        //System.out.println(mathContext.getPrecision());
        
        BigDecimal mealCost = BigDecimal.valueOf(meal_cost);
        
        BigDecimal totalTip = mealCost
                                .multiply(
                                    BigDecimal.valueOf(tip_percent)
                                    .divide(BigDecimal.valueOf(100))
                                ).round(mathContext);
        
        BigDecimal totalTax = mealCost
                                .multiply(
                                    BigDecimal.valueOf(tax_percent)
                                    .divide(BigDecimal.valueOf(100))
                                ).round(mathContext);
        
        mealCost = mealCost.add(totalTax);
        mealCost = mealCost.add(totalTip);
        
        mealCost = mealCost.round(mathContext);
        
        StringBuilder sb = new StringBuilder();
        sb.append("The total meal cost is ");
        sb.append(Math.round(mealCost.doubleValue()));
        sb.append(" dollars.");
        
        //System.out.println(totalTip.toString());
        //System.out.println(totalTax.toString());
        //System.out.println(mealCost.toString());
        
        System.out.println(sb.toString());

    }

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        double meal_cost = scanner.nextDouble();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        int tip_percent = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        int tax_percent = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        solve(meal_cost, tip_percent, tax_percent);

        scanner.close();
    }
}
```


Day 3: Intro to Conditional Statements (https://www.hackerrank.com/challenges/30-conditional-statements/problem)

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    public static void processInput(int n){
        
        //If  is odd, print Weird
        //If  is even and in the inclusive range of  to , print Not Weird
        //If  is even and in the inclusive range of  to , print Weird
        //If  is even and greater than , print Not Weird
        
        if(n % 2 == 0){
            if(n >= 2 && n <= 5){
                System.out.println("Not Weird");
            } else if(n >= 6 && n <= 20){
                System.out.println("Weird");
            } else if(n > 20){
                System.out.println("Not Weird");
            }
        } else {
            System.out.println("Weird");
        }
        
    }

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int N = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        processInput(N);
        
        scanner.close();
    }
}
```


Day 4: Class vs. Instance (https://www.hackerrank.com/challenges/30-class-vs-instance/problem)

```java
public class Person {
    private int age;	
  
	public Person(int initialAge) {
  		// Add some more code to run some checks on initialAge
       if(initialAge < 0){
            System.out.println("Age is not valid, setting age to 0.");
            this.age = 0;
        } else {
           this.age = initialAge;
        }
        
	}

	public void amIOld() {
  		// Write code determining if this person's age is old and print the correct statement:
        
        if(this.age < 13){
            System.out.println("You are young.");
        } else if(this.age >= 13 && this.age < 18){
            System.out.println("You are a teenager.");
        } else {
            System.out.println("You are old.");
        }
        
	}

	public void yearPasses() {
  		// Increment this person's age.
        this.age++;
	}
```


Day 5: Loops (https://www.hackerrank.com/challenges/30-loops/problem)

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int n = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        StringBuilder sb = null;
        for(int i =1; i<=10; i++){
            sb = new StringBuilder();
            sb.append(n).append(" x ").append(i).append(" = " + (n*i));
            System.out.println(sb.toString());
        }
        
        scanner.close();
    }
}
```



Day 6: Let's Review (https://www.hackerrank.com/challenges/30-review-loop/problem)

```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        
        Scanner scanner = new Scanner(System.in);
        
        final int totalInputs = scanner.nextInt();
        String param = null;
        String odds = null;
        String evens = null;
        
        scanner.nextLine();
        
        for(int i=0; i<totalInputs; i++){
            
            param = scanner.nextLine();
            
            odds = "";
            evens = "";
            
            for(int j = 0; j<param.length(); j++){
                
                if(j % 2 == 0){
                    evens += param.substring(j, j+1);
                } else {
                    odds += param.substring(j, j+1);
                }
                
            }
            
            System.out.println(evens + " " + odds);
            
        }
        
        
    }
}
```


Day 7: Arrays (https://www.hackerrank.com/challenges/30-arrays/problem)

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {



    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int n = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        int[] arr = new int[n];

        String[] arrItems = scanner.nextLine().split(" ");
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        StringBuilder sb = null;
        
        for (int i = n-1; i >= 0; i--) {
            
            if(sb == null){
                sb = new StringBuilder();
                sb.append(arrItems[i]);
            } else {
                sb.append(" ").append(arrItems[i]);
            }

        }
        
        System.out.println(sb.toString());
        
        scanner.close();
    }
}
```

Day 8: Dictionaries and Maps (https://www.hackerrank.com/challenges/30-dictionaries-and-maps/problem)

```java
//Complete this code or write your own from scratch
import java.util.*;
import java.io.*;

class Solution{
    public static void main(String []argh){
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        
        Map<String, Integer> map = new HashMap<>();
        
        for(int i = 0; i < n; i++){
            
            String name = in.next();
            int phone = in.nextInt();
            
            map.put(name, phone);
            
        }
        
        while(in.hasNext()){
            
            String s = in.next();
            Integer item = map.get(s);
            
            if(item != null){
                System.out.println(s + "=" + item);
            } else {
                System.out.println("Not found");
            }
            
        }
        
        in.close();
    }
}
```


Day 9: Recursion 3  (https://www.hackerrank.com/challenges/30-recursion/problem)

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    // Complete the factorial function below.
    static int factorial(int n) {

        if(n == 0) {
            return 1;
        }
        
        if(n > 1) {
            return n * factorial(n-1);
        }
        
        return n;

    }

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) throws IOException {
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        int n = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        int result = factorial(n);

        /*
        System.out.println(factorial(0));
        System.out.println(factorial(1));
        System.out.println(factorial(2));
        System.out.println(factorial(3));
        System.out.println(factorial(4));
        System.out.println(factorial(5));
        */
        
        bufferedWriter.write(String.valueOf(result));
        bufferedWriter.newLine();

        bufferedWriter.close();

        scanner.close();
    }
}
```

Day 10: Binary Numbers (https://www.hackerrank.com/challenges/30-binary-numbers/problem)

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {



    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int n = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        String bin = Integer.toBinaryString(n);
        
        int currentContinuousOnes = 0;
        int maxContinuousOnes = 0;
        
        for(int i=0; i<bin.length(); i++){
            
            if("1".equalsIgnoreCase(bin.substring(i, i+1))){
                currentContinuousOnes++;
                if(maxContinuousOnes < currentContinuousOnes){
                    maxContinuousOnes = currentContinuousOnes;
                }
            } else {
                currentContinuousOnes = 0;
            }
            
        }
        
        System.out.println(maxContinuousOnes);
        
        scanner.close();
    }
}
```


Day 11: 2D Arrays (https://www.hackerrank.com/challenges/30-2d-arrays/problem)

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {



    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int[][] arr = new int[6][6];

        for (int i = 0; i < 6; i++) {
            String[] arrRowItems = scanner.nextLine().split(" ");
            scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

            for (int j = 0; j < 6; j++) {
                int arrItem = Integer.parseInt(arrRowItems[j]);
                arr[i][j] = arrItem;
            }
        }

        System.out.println(hourglassSum(arr));
        
        scanner.close();
    }
    
    static int hourglassSum(int[][] arr) {

        int highest = Integer.MIN_VALUE;
        int current;
        
        final int loopUntil = arr.length-3;
        
        for(int i=0; i<=loopUntil; i++){
            
            for(int j=0; j<=loopUntil; j++){
                
                current = arr[i][j] + arr[i][(j+1)] + arr[i][(j+2)];
                
                current += arr[(i+1)][(j+1)];
                
                current += arr[(i+2)][j] + arr[(i+2)][(j+1)] + arr[(i+2)][(j+2)];
                
                if(current > highest){
                    highest = current;
                }
                
            }
        }
        
        return highest;

    }
    
}
```


Day 12: Inheritance (https://www.hackerrank.com/challenges/30-inheritance/problem)

```java
class Student extends Person{
    
	private int[] testScores;

    /*	
    *   Class Constructor
    *   
    *   @param firstName - A string denoting the Person's first name.
    *   @param lastName - A string denoting the Person's last name.
    *   @param id - An integer denoting the Person's ID number.
    *   @param scores - An array of integers denoting the Person's test scores.
    */
    // Write your constructor here
    public Student(String firstName, String lastName, Integer id, int[] scores){
        super(firstName, lastName, id);
        this.testScores = scores;
    }

    /*	
    *   Method Name: calculate
    *   @return A character denoting the grade.
    */
    // Write your method here
    public char calculate(){
        char grade = 'T';
        
        int total = Double.valueOf(
            Arrays.stream(testScores).average().getAsDouble()
        ).intValue();
        
        //System.out.println("total: " + total);
        
        if(total >= 90){
            grade = 'O';
        } else if(total >= 80 && total < 90) {
            grade = 'E';
        } else if(total >= 70 && total < 80) {
            grade = 'A';
        } else if(total >= 55 && total < 70) {
            grade = 'P';
        } else if(total >= 40 && total < 55) {
            grade = 'D';
        } else if(total < 40) {
            grade = 'T';
        }
        
        return grade;
    }
}
```


Day 13: Abstract Classes (https://www.hackerrank.com/challenges/30-abstract-classes/problem)

```java
// Declare your class here. Do not use the 'public' access modifier.

class MyBook extends Book {
    
    // Declare the price instance variable
    private int price;
    
    /**   
    *   Class Constructor
    *   
    *   @param title The book's title.
    *   @param author The book's author.
    *   @param price The book's price.
    **/
    // Write your constructor here
    public MyBook(String title, String author, int price){
        super(title, author);
        this.price = price;
    }
    
    /**   
    *   Method Name: display
    *   
    *   Print the title, author, and price in the specified format.
    **/
    // Write your method here
    
    public void display(){
        StringBuilder sb = new StringBuilder();
        sb.append("Title: ").append(this.title);
        sb.append("\n");
        sb.append("Author: ").append(this.author);
        sb.append("\n");
        sb.append("Price: ").append(this.price);
        System.out.println(sb.toString());
    }
    
// End class
}
```


Day 14: Scope (https://www.hackerrank.com/challenges/30-scope/problem)

```java
    public Difference(int[] elements) {
        this.elements = elements;
    }

    public void computeDifference() {
        
        Integer min = null;
        Integer max = null;
        
        for(Integer element : elements) {
            
            if(max == null || element > max) {
                max = element;
            }
            
            if(min == null || element < min) {
                min = element;
            }
            
        }
        
        //System.out.println("min: " + min);
        //System.out.println("max: " + max);
        
        maximumDifference = Math.abs(min - max);
        
    }
```


Day 15: Linked List (https://www.hackerrank.com/challenges/30-linked-list/problem)

```java    
    public static  Node insert(Node head,int data) {
        
        Node newNode = new Node(data);
        
        if(head == null) {
            return newNode;
        }
        
        Node lastNode = head;
        
        while(lastNode != null && lastNode.next != null){
            lastNode = lastNode.next;
        }
        
        lastNode.next = newNode;
        
        return head;
        
    }
```


Day 16: Exceptions - String to Integer (https://www.hackerrank.com/challenges/30-exceptions-string-to-integer/problem)

```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        String s = in.next();
        
        try{
            System.out.println(Integer.parseInt(s));
        } catch (Exception e){
            System.out.println("Bad String");
        }
        
    }
}
```


Day 17: More Exceptions (https://www.hackerrank.com/challenges/30-more-exceptions/problem)

```java
//Write your code here
class Calculator {
    
    public int power(int n, int p) {
        
        if(n < 0 || p < 0) {
            throw new IllegalArgumentException("n and p should be non-negative");
        }
        
        return Double.valueOf(Math.pow(Double.valueOf(n), Double.valueOf(p))).intValue();
    }
    
}
```


Day 18: Queues and Stacks (https://www.hackerrank.com/challenges/30-queues-stacks/problem)

```java
public class Solution {
    // Write your code here.
    
    Deque<Character> stack = new ArrayDeque<>();
    Queue<Character> queue = new LinkedList();
    
    public void pushCharacter(char c){
        stack.push(c);
    }
    
    public void enqueueCharacter(char c){
        queue.add(c);
    }
    
    public char popCharacter(){
        return stack.pop();
    }
    
    public char dequeueCharacter(){
        return queue.remove();
    }
```    


Day 19: Interfaces (https://www.hackerrank.com/challenges/30-interfaces/problem)

```java
class Calculator implements AdvancedArithmetic {
    public int divisorSum(int n) {
        
        int result = 0;
        
        for (int i = 1; i<=n; i++) {
            
            if (n % i == 0){
                result += i;
            }
            
        }
        
        return result;
    }
}
```


Day 20: Sorting (https://www.hackerrank.com/challenges/30-sorting/problem)

```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        
        Scanner in = new Scanner(System.in);
        
        int n = in.nextInt();
        int[] a = new int[n];
        
        for(int a_i=0; a_i < n; a_i++){
            a[a_i] = in.nextInt();
        }
        
        
        // Track number of elements swapped during a single array traversal
        int numberOfSwaps = 0;
        
        for (int i = 0; i < n; i++) {
            

            for (int j = 0; j < n - 1; j++) {
                // Swap adjacent elements if they are in decreasing order
                if (a[j] > a[j + 1]) {
                    //swap(a[j], a[j + 1]);
                    int aOld = a[j];
                    a[j] = a[j + 1];
                    a[j + 1] = aOld;
                    
                    numberOfSwaps++;
                }
            }

            // If no elements were swapped during a traversal, array is sorted
            if (numberOfSwaps == 0) {
                break;
            }
        }
        
        System.out.println("Array is sorted in " + numberOfSwaps + " swaps.");
        System.out.println("First Element: " + a[0]);
        System.out.println("Last Element: " + a[n-1]);
        
    }
    
}
```

Day 21: Generics (https://www.hackerrank.com/challenges/30-generics/problem)

```java
    /**
    *    Method Name: printArray
    *    Print each element of the generic array on a new line. Do not return anything.
    *    @param A generic array
    **/
    
    // Write your code here
    public void printArray(T[] array) {
        
        for(T item : array) {
            System.out.println(item);
        }
        
    }
```


Day 22: Binary Search Trees (https://www.hackerrank.com/challenges/30-binary-search-trees/problem)

```java	
    private static int maxDepth = 500;

    public static int getHeight(Node root){

        int depth = getMaxDepthRecursive(root, 0);
        
        if(depth > 0) {
            depth--;
        } 
        
        return depth;
        
    }

    public static int getMaxDepthRecursive(Node root, int depth){
        
        depth++;
        
        int left = 0;
        int right = 0;
        
        if(depth >= maxDepth) {
            throw new IllegalStateException(
                "Max depth reached in the recursion."
            );
        }
        
        if(root == null){
            throw new IllegalStateException("root must not be null.");
        }
        
        //System.out.println("depth: " + depth);
        //System.out.println("root.data: " + root.data);
        //System.out.println("root.right: " + root.right);
        //System.out.println("root.left: " + root.left);
        
        if(root.right == null && root.left == null){
            
            //System.out.println("both sides are null.");
            return depth;
            
        } else {

            if(root.right != null){
                right = getMaxDepthRecursive(root.right, depth);
            }

            if(root.left != null){
                left = getMaxDepthRecursive(root.left, depth);
            }
            
        }
        
        //System.out.println("right: " + right);
        //System.out.println("left: " + left);
        //System.out.println();
        
        if(left > right){
            return left;
        } else {
            return right;
        }
        
    }
```


Day 23: BST Level-Order Traversal (https://www.hackerrank.com/challenges/30-binary-trees/problem)

```java
    static void levelOrder(Node root){
        
        Queue<Node> queue = new LinkedList<>();
        
        if (root != null) {
            queue.add(root);
        }
        
        StringBuilder sb = new StringBuilder();
        
        while ( ! queue.isEmpty()) {
            
            Node n = queue.remove();
            
            sb.append(n.data + " ");
            
            if (n.left != null) {
                queue.add(n.left);
            }
            
            if (n.right != null) {
                queue.add(n.right);
            }
            
        }
        
        System.out.println(sb.toString());
        
    }
```


Day 24: More Linked Lists (https://www.hackerrank.com/challenges/30-linked-list-deletion/problem)

```java
    public static Node removeDuplicates(Node head) {
        
        Set<Integer> set = new TreeSet<>();
        Node next = head;
        
        while(next != null){
            set.add(next.data);
            next = next.next;
        }
        
        Node rootHead = null;
        next = null;
        
        for(Integer i : set){
            
            if(next == null){
                rootHead = new Node(i);
                next = rootHead;
            } else {
                next.next = new Node(i);
                next = next.next;
            }
            
        }

        return rootHead;
        
    }
```


Day 25: Running Time and Complexity (https://www.hackerrank.com/challenges/30-running-time-and-complexity/problem)

```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        int x;
        
        for(int i=0; i<n; i++) {
            
            x = scanner.nextInt();
            
            if(isPrime(x)){
                System.out.println("Prime");
            } else {
                System.out.println("Not prime");
            }
            
        }
        
    }
    
    public static boolean isPrime(int x) {
        
        boolean result = false;
        
        if(x == 2){
            result = true;
        } else if(x > 2 && x%2 != 0){
            
            result = true;
            
            int max = new Double(Math.ceil(Math.sqrt(x))).intValue();
            
            for(int i=3; i<=max; i=i+2){
                
                //System.out.println("x: " + x + " i: " + i + " max: " + max + " x % i: " + x % i);
                
                if(x % i == 0) {
                    result = false;
                    break;
                }
                
            }
            
        }
        
        return result;
        
    }
    
}
```


Day 26: Nested Logic (https://www.hackerrank.com/challenges/30-nested-logic/problem)

```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.time.*;
import java.util.regex.*;

public class Solution {

    public static final int FINE_PER_DAY_IN_HACKOS = 15;
    public static final int FINE_PER_MONTH_IN_HACKOS = 500;
    public static final int FINE_PAST_A_YEAR_IN_HACKOS = 10000;
    
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        int returnedDay = scanner.nextInt();
        int returnedMonth = scanner.nextInt();
        int returnedYear = scanner.nextInt();
        
        int expectedDay = scanner.nextInt();
        int expectedMonth = scanner.nextInt();
        int expectedYear = scanner.nextInt();
        
        int totalFine = 0;
        
        LocalDate returnedDate = LocalDate.of(returnedYear, returnedMonth, returnedDay);
        LocalDate dueDate = LocalDate.of(expectedYear, expectedMonth, expectedDay);
        
        Period diff = Period.between(dueDate, returnedDate);
        int diffInDays = diff.getDays();
        int diffInMonths = returnedMonth - expectedMonth;
        int diffInYears = returnedYear - expectedYear;
        
        /*
        System.out.println(diff.getDays());
        System.out.println(diff.getMonths());
        System.out.println(diff.getYears());
        System.out.println();
        System.out.println(diffInDays);
        System.out.println(diffInMonths);
        System.out.println(diffInYears);
        */
        
        if(diffInYears > 0) {
            totalFine = FINE_PAST_A_YEAR_IN_HACKOS;
        } else if(diffInMonths > 0) {
            totalFine = diffInMonths * FINE_PER_MONTH_IN_HACKOS;
        } else {
            totalFine = diffInDays * FINE_PER_DAY_IN_HACKOS;
        }
        
        /*
        if(diff.getYears() > 0) {
            totalFine = FINE_PER_MONTH_IN_HACKOS;
        } else if(diff.getMonths() > 0) {
            totalFine = diff.getMonths() * FINE_PER_MONTH_IN_HACKOS;
        } else {
            totalFine = diff.getDays() * FINE_PER_DAY_IN_HACKOS;
        }
        */
        
        if (returnedDate.isEqual(dueDate) || returnedDate.isBefore(dueDate)) {
            totalFine = 0;
        } else if (
            returnedDate.getMonth() == dueDate.getMonth() 
            && returnedDate.getYear() == dueDate.getYear()
        ) {
            totalFine = FINE_PER_DAY_IN_HACKOS * (
                returnedDate.getDayOfMonth() - dueDate.getDayOfMonth()
            );
        } else if (returnedDate.getYear() == dueDate.getYear()) {
            totalFine = FINE_PER_MONTH_IN_HACKOS
                * (returnedDate.getMonthValue() - dueDate.getMonthValue());
        } else {
            totalFine = FINE_PAST_A_YEAR_IN_HACKOS;
        }
        
        System.out.println(totalFine);
        
    }
}
```


Day 27: Testing (https://www.hackerrank.com/challenges/30-testing/problem)

```java
    static class TestDataEmptyArray {
        
        public static int[] get_array() {
            return new int[0];
        }
        
    }

    static class TestDataUniqueValues {
        
        public static int[] get_array() {
            return new int[]{11,2,3};
        }

        public static int get_expected_result() {
            return 1;
        }
    }

    static class TestDataExactlyTwoDifferentMinimums {
        public static int[] get_array() {
            return new int[]{4,4};
        }

        public static int get_expected_result() {
            return 0;
        }
    }
```


Day 28: RegEx, Patterns, and Intro to Databases (https://www.hackerrank.com/challenges/30-regex-patterns/problem)

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {



    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int N = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        List<String> list = new ArrayList<>();
        
        for (int NItr = 0; NItr < N; NItr++) {
            String[] firstNameEmailID = scanner.nextLine().split(" ");

            String firstName = firstNameEmailID[0];

            String emailID = firstNameEmailID[1];
            
            if(emailID != null && emailID.toLowerCase().contains("@gmail.com")) {
                list.add(firstName);
            }
            
        }

        Collections.sort(list);
        list.forEach(o -> System.out.println(o));
        
        scanner.close();
    }
}
```


Day 29: Bitwise AND (https://www.hackerrank.com/challenges/30-bitwise-and/problem)

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {



    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        
        int t = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        for (int tItr = 0; tItr < t; tItr++) {
            
            String[] nk = scanner.nextLine().split(" ");
            int n = Integer.parseInt(nk[0]);
            int k = Integer.parseInt(nk[1]);
            
            
            int maxAB = 0;
            int AB = 0;
            
            for(int a=1; a<n; a++) {
                
                for(int b=a+1; b<=n; b++) {
                    AB = a&b;
                    
                    if(AB<k && AB > maxAB){
                        maxAB = AB;
                    }
                    
                }
                
            }
            
            System.out.println(maxAB);
            
        }

        scanner.close();
    }
}
```

Douglas Souza
[![LinkedIn Logo](./Linked_in.png)](https://www.linkedin.com/in/douglas-souza-mba-it-developer/)https://www.linkedin.com/in/douglas-souza-mba-it-developer/