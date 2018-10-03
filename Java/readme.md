# Douglas Souza
# Hacker Rank - Java Challenges - Submissions (Medium/Hard)

[![Hacker Rank Logo](https://hrcdn.net/hackerrank/assets/brand/h_mark_sm-9c05999c62674028552f4e813728e591.svg)](https://www.hackerrank.com/douglas15) - [![Golden Badges](../badges.png)](https://www.hackerrank.com/douglas15)


- ### Java Regex (https://www.hackerrank.com/challenges/java-regex/problem)


```java
//Write your code here
class MyRegex {
    //public String pattern = "^(([0-9]{1,3})\\.){4}$";
    //public String pattern = "^[0-9]{1,3}\\.[0-9]{1,3}\\.[0-9]{1,3}\\.[0-9]{1,3}$";
    //public String pattern = "^[0-2]{0,1}[0-9]{1,2}\\.[0-2]{0,1}[0-9]{1,2}\\.[0-2]{0,1}[0-9]{1,2}\\.[0-2]{0,1}[0-9]{1,2}$";
    //public String pattern = "^(([0-2]{1}[0-5]{2}\\.)|([0-9]{1,2}\\.)){3}(([0-2]{1}[0-5]{2})|([0-9]{1,2})){1}$";
    public String pattern = "^(([01]?\\d\\d?|2[0-4]\\d|25[0-5])\\.){3}([01]?\\d\\d?|2[0-4]\\d|25[0-5])$";
    
    public MyRegex(){
        
    }

    
}
```


- ### Java Regex 2 - Duplicate Words (https://www.hackerrank.com/challenges/duplicate-word/problem)


```java
import java.util.Scanner;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DuplicateWords {

    public static void main(String[] args) {

        String regex = "\\b(\\w+)(\\W+\\1\\b)+";
        Pattern p = Pattern.compile(regex, Pattern.CASE_INSENSITIVE);

        Scanner in = new Scanner(System.in);
        int numSentences = Integer.parseInt(in.nextLine());
        
        while (numSentences-- > 0) {
            String input = in.nextLine();
            
            Matcher m = p.matcher(input);
            
            // Check for subsequences of input that match the compiled pattern
            while (m.find()) {
                input = input.replaceAll(m.group(), m.group(1));
            }
            
            // Prints the modified sentence.
            System.out.println(input);
        }
        
        in.close();
    }
}
```


- ### Tag Content Extractor (https://www.hackerrank.com/challenges/tag-content-extractor/problem)


```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        int testCases = Integer.parseInt(scan.nextLine());
        
        while (testCases-- > 0) {
            String line = scan.nextLine();
            
            boolean matchFound = false;
            Pattern r = Pattern.compile("<(.+)>([^<]+)</\\1>");
            Matcher m = r.matcher(line);

            while (m.find()) {
                System.out.println(m.group(2));
                matchFound = true;
            }
            if ( ! matchFound) {
                System.out.println("None");
            }
        }
    }
}
```


- ### Java BigDecimal (https://www.hackerrank.com/challenges/java-bigdecimal/problem)


```java
        //Write your code here

        List<String> list = Arrays.stream(s).filter(o->o!=null).sorted((s2,s1)->{
           return new BigDecimal(s1).compareTo(new BigDecimal(s2));
        }).collect(java.util.stream.Collectors.toList());

        s = list.toArray(s);
```


- ### Java 1D Array (Part 2) (https://www.hackerrank.com/challenges/java-1d-array/problem)


```java
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int T = scan.nextInt();
        while (T-- > 0) {
            int n = scan.nextInt();
            int m = scan.nextInt();
            int [] array = new int[n];
            for (int i = 0; i < n; i++) {
                array[i] = scan.nextInt();
            }
            System.out.println(isSolvable(array, m, 0) ? "YES" : "NO");
        }
        scan.close();
    }
    
    /* Basically a depth-first search (DFS). 
       Marks each array value as 1 when visiting (Side-effect: alters array) */
    private static boolean isSolvable(int[] array, int m, int i) {
        /* Base Cases */
        if (i < 0 || array[i] == 1) {
            return false;
        } else if (i + 1 >= array.length || i + m >= array.length) {
            return true;
        }
        
        array[i] = 1; // marks as visited

        /* Recursive Cases (Tries +m first to try to finish game quickly) */
        return isSolvable(array, m, i + m) || 
               isSolvable(array, m, i + 1) || 
               isSolvable(array, m, i - 1);
    }
}
```


- ### Java Stack (https://www.hackerrank.com/challenges/java-stack/problem)


```java
import java.util.*;
import java.util.function.*;

class Solution{
    
	public static void main(String []argh) {
        
		Scanner sc = new Scanner(System.in);
		
        Map<String, Consumer<Deque<String>>> mapCharAction = buildCharActionMap();
        Deque<String> stack = new ArrayDeque<String>();
        
		while (sc.hasNext()) {
            
            String input=sc.next();
            boolean isValid = true;
            stack.clear();
            
            //Count the chars from input
            for(int i=0; i<input.length(); i++) {
                
                String key = String.valueOf(input.charAt(i));
                
                if(mapCharAction.containsKey(key)){
                    
                    try{
                        mapCharAction.get(key).accept(stack);
                    } catch (IllegalArgumentException iae) {
                        isValid = false;
                        break;
                    }
                    
                }
                
            }
            
            System.out.println(isValid && stack.isEmpty());
            
		}
        
	}
    
    public static Map<String, Consumer<Deque<String>>> buildCharActionMap(){
        
        Map<String, Consumer<Deque<String>>> mapCharAction = new HashMap<>();
        
        mapCharAction.put("(", (Deque<String> stk)->stk.push("("));
        mapCharAction.put("[", (Deque<String> stk)->stk.push("["));
        mapCharAction.put("{", (Deque<String> stk)->stk.push("{"));
     
        mapCharAction.put(")", (Deque<String> stk)->{
            if("(".equals(stk.peek())) { 
                stk.pop();
            } else {
                throw new IllegalArgumentException("Unable to complete the action requested.");
            }
        });
        
        mapCharAction.put("]", (Deque<String> stk)->{
            if("[".equals(stk.peek())) { 
                stk.pop();
            } else {
                throw new IllegalArgumentException("Unable to complete the action requested.");
            }
        });
        
        mapCharAction.put("}", (Deque<String> stk)->{
            if("{".equals(stk.peek())) { 
                stk.pop();
            } else {
                throw new IllegalArgumentException("Unable to complete the action requested.");
            }
        });
        
        return mapCharAction;
        
    }
    
}
```


- ### Java Comparator (https://www.hackerrank.com/challenges/java-comparator/problem)


```java
// Write your Checker class here
class Checker implements Comparator<Player> {
    
    public Checker(){
    }
    
    @Override
    public int compare(Player p1, Player p2){
        
        if(p1 == null && p2 == null) {
            return 0;
        } else if(p1 == null || p2 == null) {
            
            if(p1 != null && p2 == null) {
                return 1;
            } else {
                return -1;
            }
            
        }
        
        if(p1.score == p2.score) {
            
            
            if(p1.name == null || p2.name == null){
                return 0;
            } else if(p1.name == null || p2.name == null){
                
                if(p1.name == null) {
                    return -1;
                }
                
                if(p2.name == null) {
                    return 1;
                }
                
            }
            
            return p1.name.compareTo(p2.name);
            
        } else {
            return Integer.compare(p2.score, p1.score);
        }

    }
    
}
```


- ### Java Dequeue (https://www.hackerrank.com/challenges/java-dequeue/problem)


```java
 import java.util.*;
public class test {
    public static void main(String[] args) {
        HashMap<Integer, Integer> map = new HashMap<>();
        Deque<Integer> deque          = new ArrayDeque<>();
        
        Scanner scan = new Scanner(System.in);
        int n = scan.nextInt();
        int m = scan.nextInt();        
        int max = map.size();
        
        for (int i = 0; i < n; i++) {
            /* Remove old value (if necessary) */
            if (i >= m) {
                int old = deque.remove();
                if (map.get(old) == 1) {
                    map.remove(old);
                } else {
                    map.put(old, map.get(old) - 1);
                }
            }
            /* Add new value */
            int num = scan.nextInt();
            deque.add(num);
            map.merge(num, 1, Integer::sum);
            
            max = Math.max(max, map.size());
                        
            /* If all integers are unique, break out of loop */
            if (max == m) {
                break;
            }
        }
        
        scan.close();
        System.out.println(max);
    }
}

/*
    import java.util.*;
    public class test {
        public static void main(String[] args) {
            
            Scanner in = new Scanner(System.in);
            
            final int n = in.nextInt();
            final int m = in.nextInt();
            final int mm = m-2;

            Deque<Integer> deque = new ArrayDeque<>(m);
            Set<Integer> uniqueNumbers = new LinkedHashSet<>(m);
            //Set<Integer> uniqueNumbers = new HashSet<>(m);
            //Map<Integer, Integer> uniqueNumbers = new HashMap<>(m);
            //int[][] uniqueNumbers = new int[m][1];
            int maxUniqueNumbers = 0;
            
            int a, num;
            boolean containedNumberBefore = false;

            for (int i = 0; i < n; i++) {
                
                num = in.nextInt();
                
                //deque.addLast(num);
                deque.addFirst(num);
                
                if(uniqueNumbers.add(num)) {
                    maxUniqueNumbers++;
                    //System.out.println("added " + addedNewUnique + " " + num);
                    //Stop the procedure as maxUniqueNumbers cannot become larger.
                    if(maxUniqueNumbers == m){
                        break;
                    }
                    
                }
                
                //System.out.println("deque: " + Arrays.toString(deque.toArray()));
                //System.out.println("set: " + Arrays.toString(uniqueNumbers.toArray()));
                
                //System.out.println("i: " + i + " num: " + num + " max: " + maxUniqueNumbers);
                //if(deque.size() == m){
                if(i > mm){
                    //System.out.println("mm: " + mm + " deque.size(): " + deque.size());
                    
                    //if(maxUniqueNumbers < uniqueNumbers.size()){
                    //    maxUniqueNumbers = uniqueNumbers.size();
                    //}
                    
                    //Stop the procedure as maxUniqueNumbers cannot become larger.
                    //if(maxUniqueNumbers == m){
                    //    break;
                    //}
                    
                    
                    containedNumberBefore = deque.contains(deque.peekLast());
                    
                    //a = deque.removeFirst();
                    a = deque.removeLast();
                    
                    
                    
                    //Only removes the number if it was included in this iteration.
                    //If it was already present in the set it will not be removed this iteration.
                    if(containedNumberBefore == false) {
                        //boolean removed = 
                        uniqueNumbers.remove(a);
                        //System.out.println("removed " + removed + " " + a);
                        maxUniqueNumbers--;
                        //uniqueNumbers.rem
                    }
                    
                }
                //System.out.println("");
            }
            
            System.out.println(maxUniqueNumbers);
            
        }
        
    }
/*/
```


- ### Java Priority Queue (https://www.hackerrank.com/challenges/java-priority-queue/problem)


```java
import java.util.*;

/*
 * Create the Student and Priorities classes here.
 */

class Student implements Comparable<Student> {
    
    private String name;
    private double CGPA;
    private int id;
    
    public Student(){
        
    }
    
    public Student(int id, String name, double gpa){
        super();
        this.id = id;
        this.name = name;
        this.CGPA = gpa;
    }
    
    public String getName(){
        return this.name;
    }
    
    public double getCGPA() {
        return this.CGPA;
    }
    
    public int getId() {
        return this.id;
    }
    
    public int compare(Student a, Student b){

        if(a != null && b != null){
            int GPAComparison = Double.compare(b.getCGPA(), a.getCGPA());
            if(GPAComparison != 0){
                return GPAComparison;
            } else if(a.getName() != null && b.getName() !=null){
                int nameComparison = a.getName().compareTo(b.getName());
                if(nameComparison != 0){
                    return nameComparison;
                } else {
                    return Integer.compare(a.getId(), b.getId());
                }
            }
        } 
        return 0;

    }
    
    public int compareTo(Student student){
        return compare(this, student);
    }
    
}

class Priorities {
    
    public List<Student> getStudents(List<String> events) {
        
        PriorityQueue<Student> students = new PriorityQueue();
        
        for(String event : events) {
            
            if("".equalsIgnoreCase(event) == false) {
                
                if("SERVED".equalsIgnoreCase(event)){
                    Student polled = students.poll();
                } else {
                    
                    String[] values = event.split(" ");
                    
                    Student s = new Student(
                        Integer.parseInt(values[3]), 
                        values[1], 
                        Double.valueOf(values[2])
                    );

                    students.add(s);
                    
                }
                
            }
            
        }
        
        LinkedList linkedList = new LinkedList();
        
        while(students.peek() != null){
            linkedList.add(students.poll());
        }
        
        return linkedList;
        
    }
    
}
```


- ### Can You Access? (https://www.hackerrank.com/challenges/can-you-access/problem)


```java
			//Write your code here
            o = new Inner().new Private();

            System.out.println(num + " is " + ((Solution.Inner.Private)o).powerof2(num));
```


- ### Prime Checker (https://www.hackerrank.com/challenges/prime-checker/problem)


```java
import static java.lang.System.in;

class Prime {
    
    public void checkPrime(int... numbers) {
        
        StringBuilder sb = new StringBuilder();
        
        for(int number : numbers) {
            
            boolean isPrime = BigInteger.valueOf(number).isProbablePrime(Integer.MAX_VALUE);
            
            if(isPrime == false) {
                continue;
            }
            
            sb.append(number).append(" ");
                
        }
        
        if(sb != null) {
            System.out.println(sb.toString().trim());
        }
        
    }
    
}
```


- ### Java Visitor Pattern (https://www.hackerrank.com/challenges/java-vistor-pattern/problem)


```java
class SumInLeavesVisitor extends TreeVis {
    private int result = 0;

    public int getResult() {
        return result;
    }

    public void visitNode(TreeNode node) {
        // do nothing
    }

    public void visitLeaf(TreeLeaf leaf) {
        result += leaf.getValue();
    }
}

class ProductOfRedNodesVisitor extends TreeVis {
    private long result = 1;
    private final int M = 1000000007;

    public int getResult() {
        return (int) result;
    }

    public void visitNode(TreeNode node) {
        if (node.getColor() == Color.RED) {
            result = (result * node.getValue()) % M;
        }
    }

    public void visitLeaf(TreeLeaf leaf) {
        if (leaf.getColor() == Color.RED) {
            result = (result * leaf.getValue()) % M;
        }
    }
}

class FancyVisitor extends TreeVis {
    private int nonLeafEvenDepthSum = 0;
    private int greenLeavesSum = 0;

    public int getResult() {
        return Math.abs(nonLeafEvenDepthSum - greenLeavesSum);
    }

    public void visitNode(TreeNode node) {
        if (node.getDepth() % 2 == 0) {
            nonLeafEvenDepthSum += node.getValue();
        }
    }

    public void visitLeaf(TreeLeaf leaf) {
        if (leaf.getColor() == Color.GREEN) {
            greenLeavesSum += leaf.getValue();
        }
    }
}

public class Solution {
    
    private static int [] values;
    private static Color [] colors;
    private static HashMap<Integer, HashSet<Integer>> map;
    
    public static Tree solve() {
        
        Scanner scan = new Scanner(System.in);
        int numNodes = scan.nextInt();
        
        /* Read and save nodes and colors */
        values = new int[numNodes];
        colors = new Color[numNodes];
        map = new HashMap<>(numNodes);
        
        for (int i = 0; i < numNodes; i++) {
            values[i] = scan.nextInt();
        }
        
        for (int i = 0; i < numNodes; i++) {
            colors[i] = scan.nextInt() == 0 ? Color.RED : Color.GREEN;
        }
        
        /* Save edges */
        for (int i = 0; i < numNodes - 1; i++) {
            
            int u = scan.nextInt();
            int v = scan.nextInt();
            
            /* Edges are undirected: Add 1st direction */
            HashSet<Integer> uNeighbors = map.get(u);
            if (uNeighbors == null) {                
                uNeighbors = new HashSet<>();
                map.put(u, uNeighbors);
            }
            
            uNeighbors.add(v);
            
            /* Edges are undirected: Add 2nd direction */
            HashSet<Integer> vNeighbors = map.get(v);
            if (vNeighbors == null) {
                vNeighbors = new HashSet<>();
                map.put(v, vNeighbors);
            }
            
            vNeighbors.add(u);
            
        }
        
        scan.close();
        
        /* Handle 1-node tree */
        if (numNodes == 1) {
            return new TreeLeaf(values[0], colors[0], 0);
        }
        
        /* Create Tree */
        TreeNode root = new TreeNode(values[0], colors[0], 0);
        addChildren(root, 1);
        
        return root;
        
    }

    /* Recursively adds children of a TreeNode */
    private static void addChildren(TreeNode parent, Integer parentNum) {
        
        /* Get HashSet of children and loop through them */
        for (Integer treeNum : map.get(parentNum)) {
            
            map.get(treeNum).remove(parentNum); // removes the opposite arrow direction
            
            /* Add child */
            HashSet<Integer> grandChildren = map.get(treeNum);
            
            boolean childHasChild = (grandChildren != null && !grandChildren.isEmpty());
            
            Tree tree;
            
            if (childHasChild) {
                
                tree = new TreeNode(
                    values[treeNum - 1],
                    colors[treeNum - 1], 
                    parent.getDepth() + 1
                );
                
            } else {
                
                tree = new TreeLeaf(
                    values[treeNum - 1], 
                    colors[treeNum - 1], 
                    parent.getDepth() + 1
                );
                
            }
            parent.addChild(tree);

            /* Recurse if necessary */
            if (tree instanceof TreeNode) {
                addChildren((TreeNode) tree, treeNum);
            }
            
        }
        
    }
```


- ### Java Annotations (https://www.hackerrank.com/challenges/java-annotations/problem)


```java
import java.lang.annotation.*;
import java.lang.reflect.*;
import java.util.*;

@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
@interface FamilyBudget {
	String userRole() default "GUEST";
	int budgetLimit() default 0;
}

class FamilyMember {
	@FamilyBudget(userRole="SENIOR", budgetLimit=100)
	public void seniorMember(int budget, int moneySpend) {
		System.out.println("Senior Member");
		System.out.println("Spend: " + moneySpend);
		System.out.println("Budget Left: " + (budget - moneySpend));
	}

	@FamilyBudget(userRole="JUNIOR", budgetLimit=50)
	public void juniorUser(int budget, int moneySpend) {
		System.out.println("Junior Member");
		System.out.println("Spend: " + moneySpend);
		System.out.println("Budget Left: " + (budget - moneySpend));
	}
}

public class Solution {
	public static void main(String[] args) {
		Scanner in = new Scanner(System.in);
		int testCases = Integer.parseInt(in.nextLine());
		while (testCases > 0) {
			String role = in.next();
			int spend = in.nextInt();
			try {
				Class annotatedClass = FamilyMember.class;
				Method[] methods = annotatedClass.getMethods();
				for (Method method : methods) {
					if (method.isAnnotationPresent(FamilyBudget.class)) {
						FamilyBudget family = method
								.getAnnotation(FamilyBudget.class);
						String userRole = family.userRole();
						int budgetLimit = family.budgetLimit();
						if (userRole.equals(role)) {
							if((budgetLimit - spend) >= 0){
								method.invoke(FamilyMember.class.newInstance(),
										budgetLimit, spend);
							}else{
								System.out.println("Budget Limit Over");
							}
						}
					}
				}
			} catch (Exception e) {
				e.printStackTrace();
			}
			testCases--;
		}
	}
}
```


- ### Java Lambda Expressions (https://www.hackerrank.com/challenges/java-lambda-expressions/problem)


```java
    public PerformOperation isOdd() {
        PerformOperation op = (int a)->{
            
            if(a == 0) {
                return false;
            } else {
                return (a % 2 != 0);
            }
            
        };

        return op;
    }

    public PerformOperation isPrime() {
        PerformOperation op = (int a)->{
            return java.math.BigInteger.valueOf(a).isProbablePrime(Integer.MAX_VALUE);
        };

        return op;
    }

    public PerformOperation isPalindrome() {
        PerformOperation op = (int a)->{
            String reversed = new StringBuilder(String.valueOf(a)).reverse().toString();
            
            return reversed.equalsIgnoreCase(String.valueOf(a));
        };

        return op;
    }

}
```


- ### Java MD5 (https://www.hackerrank.com/challenges/java-md5/problem)


```java
import java.io.*;
import java.util.*;
import java.security.MessageDigest;
import java.security.*;

public class Solution {

    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        String input = scanner.nextLine();
        
        try {
            
            MessageDigest md = MessageDigest.getInstance("MD5");
            byte[] bytes = md.digest(input.getBytes());
            
            
            for (byte b : bytes) {
                System.out.printf("%02x", b);
            }
            
        } catch (NoSuchAlgorithmException nsae) {
            nsae.printStackTrace();
        }
        
    }
}
```


- ### Java SHA-256 (https://www.hackerrank.com/challenges/sha-256/problem)


```java
import java.io.*;
import java.util.*;
import java.security.*;

public class Solution {

    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        
        String input = scanner.nextLine();
        
        try {
            
            MessageDigest md = MessageDigest.getInstance("SHA-256");
            byte[] bytes = md.digest(input.getBytes());
            
            
            for (byte b : bytes) {
                System.out.printf("%02x", b);
            }
            
        } catch (NoSuchAlgorithmException nsae) {
            nsae.printStackTrace();
        }
        
    }
}
```


[Douglas Souza](https://www.linkedin.com/in/douglas-souza-mba-it-developer/) - https://www.linkedin.com/in/douglas-souza-mba-it-developer/