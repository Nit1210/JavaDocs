# JavaDocs
This repository is about all the learning concepts which got into my attention.
JAVA Learning Material
How programming works in Java?
	So, basically all programming languages work in executing human given inputs to machine in a machine understandable language which is binary(0,1). The conversation process human given inputs (which is instructions given in java) were converted to byte code and stored in a .class file in java by the compiler. And that .class file can be executed in any java platform with JVM. To put it simple the instructions from the java code is compiled by the java complier which converts the file to byte code(machine understandable) and then the converted code is executed by the JVM.
How is the bytecode conversion takes place and what are required materials for it in java?
	So, for a give java file to execute you need java development tool kit(JDK) which contains JRE(Java Run Time Environment) and JRE contains java library and JVM(Java virtual machine). In order for the java code to be executed we need both JDK and JRE. JDK is responsible for compiling, developing and debugging the code. When we are trying perform those actions it means we are using JDK. We need JDK for the  
What does JDK contain?
	JDK is used to develop a application or a applet. JDK contains compiler(javac), interpreter(java), archiver(jar) etc.
	Along with the above items. JDK also contains JRE(Java Runtime Environment).
	JRE is responsible for providing tools and libraries necessary for running the java code.
	Along with the tools and library JRE contains JVM(Java virtual Machine).
	JVM is a virtual machine which is responsible for the execution of the bytecode (compiled code) in java. It is called virtual machine because it’s a program.
	In order to reduce the complexity of the JVM, JIT(Just in Time) interpreter in included in JVM.
Link : https://www.tutorialspoint.com/differences-between-jdk-jre-and-jvm#:~:text=JDK%20is%20primarily%20used%20for,provide%20these%20implementations%20to%20JRE.

What is Abstraction?
	Abstraction is a concept in java which is used to show only necessary details and hide the unnecessary details to the user. Abstract is a direct key word which can be used to implement abstract. Abstract class can contain abstract method whereas normal class cannot have abstract method. We can use Abstract class using extend keyword to normal class. As we are extending a normal class and using the abstract class/method it should be public. That’s the reason for the abstract class need to be public.
	Similar to abstraction and to achieve data hiding feature we also use another process called interface. All the methods declared in interface are abstract methods. Same like abstract interfaces cannot be declared as private or protected. Uses of interfaces are we need not declare abstract methods in interface as by default all the methods are abstract in interface. And also interface can be extended by interface and also interface is flexible to implement n number of interfaces by a class.
Can we instantiate abstract class?
	No, we cannot instantiate abstract class. We need to create another normal class and then extent the abstract class to it. Now the created class can be instantiated, and we can use the abstract class through it.
When an abstract class method has the same method in a subclass. Which method is complied when the subclass method is initiated?
	The method which is present in the subclass is overridden by the abstract class. Which means that the method in the subclass is executed not the abstract class until we use the keyword. “super” to class the method. When we use the super.method_name() then the abstract class method is executed.
Example:
abstract class AbstractClass {
    public void method() {
        System.out.println("AbstractClass method");
    }
}

class SubClass extends AbstractClass {
    @Override
    public void method() {
        super.method(); // Invoke the superclass method
        System.out.println("SubClass method");
    }
}

public class Main {
    public static void main(String[] args) {
        SubClass obj = new SubClass();
        obj.method();
    }
}
Output:

AbstractClass method
SubClass method


What happens when an abstract class is extended by another abstract class?
	
What is Coupling? And why classes or code should have less coupling?
	Coupling is the measure of dependency on one class to another. IT means that if we make some changes in one class how much the dependent class is affected. In programming it is not good when other codes or classes are more effected when you modify a code / class. That the reason why classes or code should have less coupling.

What is cohesive? And why the cohesiveness should be more in java?
	Cohesiveness is the refers of a class. Like how far it is understandable. If we create a class that class should satisfy the agenda of the class and it should be understandable.

Association,composition.

What is runtime polymorphism ? Why does it not occur when a function is declared in static?
Run time polymorphism is using the instance of a parent class to act accordingly to the child class. Suppose Parent p = new child1(); and Parent p = new child2(); is initiated. Even if the same child classes has same methods they are called accordingly to the child classes.In short it the ability to utilize the invocation of parent class to invoke or perform the operations of overridden methods according to the actual subclasses at runtime.  This happens in the runtime and as the static declared methods are resolved at the compilation itself . As the method resolution(binding process of which method to be invoked when a method is called upon an object ) is achieved in the compile time itself, the method do not participate in runtime or in runtime polymorphism. Usually the method resolution is achieved in runtime but when declared static it is achieved on compilation time itself.

What is string constant pool?

 
How should a variable be declared?
	As there are some reserved words, rule stating we cannot use numbers in start of declaring a variable. There are some rules or suggestions to declare a variable. They are: 
1.	If it is a single word variable, then that variable name can be declared in all lowercases. E.g.: first 
2.	If it is a double word or more words variable, then it is suggested to use the second word 1st letter as Capital e.g.: firstSecond.
3.	It is also suggested to provide full meaning full name to the variable instead of abbreviations or short cuts.

What is a Constructor?
	
What are access modifiers and how are they used.
	Public , Private ,protect and defaults are the 4 access modifiers. As the name implies they are used to access the data. Different access modifiers allow different criteria’s for accessing data from the class.
1.	Public class can be used to access the class anywhere which is even outside the package.
2.	Private class can be accessed with in the class.
3.	Protected can be used to be accessed anywhere within the package and subclass.
4.	Default which means we declare nothing to the class. Default class can be access anywhere within the package. 
What are local, Static and instance variables in java?

Which one is suggested to be used for better programing in the industry Switch or if else statements?

What is static class and variable?

 What is static variable in a class?
Static Variable is a constant variable throughout the class. When a variable is declared static we can directly call it in the other class without creating a object.

Note: On difference from java to python is we can print declared variable names in python were as we cannot access variable names in java. In python the variable names can be access using globals().items() function.

Why final class cannot be extended?
	Final class cannot be extended because the designer has marked the class as final indicating it cannot be modified further. As a Security purpose it is to ensure that the class cannot be accessed or to make any changes in it. The java compiler also performs some optimization while compiling final methods/classes. 
What is the use of .intern() and where is it used?
	The Strings when declared with same word will be pointing to the same pointers. Whereas if we declare the same words using new String keyword they an new word is created outside the string constant pool and the variable is pointed to the new pointer. In this case when we use S1==S2, considering they are variables for the normally declared string and string declared with new keyword. The result will be false even if the values are same. For that to not happen and the result to be accuracte we use .intern() at the string declareation.
	Eg:
String S1=”hello”;
String S2= new String(“hello”);
System.Out.println(S1==S2); //as new pointer is allocated to S2 the value will be false.
Output : false
String S1=”hello”;
String S2= new String(“hello”).intern();
System.Out.println(S1==S2);
Output: True
Note: Strings are objects and they are immutable(values will not be changed once created) even if you update the string value the value existing in the pointer do not change. Instead, a new pointer with the updated value is created.
Note: In realtime industry work arraylist is morelikely to be used for access. Where as theoretically linkedlist should perform quicker for updating and deleting but in realtime arraylist is faster in any.
Sets:
HashSet randomly stores the data where as linkedHashSet maintains the insertion order of the data.
Arraylist and HashMaps are widely used in the industry. While trying to retrieve a JSON file HashMaps are used as the JSON values are associated with key values.
If we want to retrieve the data fast and doesn’t care about the insertion order. Then for fast operation we can used HashMap’s.
If we care about the order of insertion then LinkedHashMaps are suggested to use.
If we want the data to be stored in a sorting order then TreehashMaps are used.

Syntax to remember:
Array copying:
Systemarraycopy();

Arraylist iteration:
Arraylist <String >Arrayname=new Arraylist<>;
Arrayname.foreach (emp->{
System.out.println(emp);
});

What is Java Enterprise Edition? How is it different from other editions?






"Dear Silas,
I hope this message finds you well. I recently graduated with an MS-CSE degree from Kennesaw State University and have gained over 2 years of experience in the Financial Services sector before my Masters. I am currently seeking an opportunity to apply my newly acquired software skills in a professional setting through an unpaid or minimum-paid internship. I would greatly appreciate it if you could consider providing me with an opportunity at your esteemed company. I am eager to contribute and learn from the industry's best. Please let me know your thoughts on this matter.
Thank you for your time and consideration.
Sincerely,
[Your Name]"
![image](https://github.com/Nit1210/JavaDocs/assets/98055206/7b009cd2-0169-447a-8238-e615e749e60f)
