Java Interview preparation:
_____________________________________________________

The core concepts of Java.
1. Abstraction: Abstraction is a process where you show only “relevant” data and “hide” unnecessary details of an object from the user.
Abstraction can be achieved using the abstract class, abstract methods, and interface. interfaces we can achieve 100% abstraction
2. encapsulation-mechanism that binds together code and the data it manipulates and keeps both safe from outside interference and misuse.
example java bean with private members and public methods/getter setters
3. Inheritance - Inheritance is the mechanism by which an object acquires the some/all properties of another object. Achieved using extends keyword
4. Polymorphism - Polymorphism means to process objects differently based on their data type. Implemented using Overloading and Overriding.

What is the role for a classloader in Java?
The Java ClassLoader is a part of the Java Runtime Environment that dynamically loads Java classes into the Java Virtual Machine

A Java Classloader is of three types:

BootStrap ClassLoader: A Bootstrap Classloader is a Machine code which kickstarts the operation when the JVM calls it. It is not a java class. Its job is to load the first pure Java ClassLoader. Bootstrap ClassLoader loads classes from the location rt.jar. Bootstrap ClassLoader doesn’t have any parent ClassLoaders. It is also called as the Primodial ClassLoader.
Extension ClassLoader: The Extension ClassLoader is a child of Bootstrap ClassLoader and loads the extensions of core java classes from the respective JDK Extension library. It loads files from jre/lib/ext directory or any other directory pointed by the system property java.ext.dirs.
System ClassLoader: An Application ClassLoader is also known as a System ClassLoader. It loads the Application type classes found in the environment variable CLASSPATH, -classpath or -cp command line option. The Application ClassLoader is a child class of Extension ClassLoader.

Collections framework?

Difference between throw and throws in Java?
Main difference between these two is that one declares exception thrown by a Java method while other is actually used to throw Exception
String class
Multithreading
Serialization

Hashmap internal working?  

Difference between HashMap and HashTable.

Ans: Difference between HashMap and HashTable can be seen below:

HashMap													HashTable
Methods are not synchronized							Key methods are synchronized
Not thread safety										Thread safety
Iterator is used to iterate the values					Enumerator is used to iterate the values
Allows one null key and multiple null values			Doesn’t allow anything that is null
Performance is high than HashTable						Performance is slow


Difference between HashSet and TreeSet.

Ans: Difference between HashSet and TreeSet can be seen below:

HashSet												TreeSet
Inserted elements are in random order				Maintains the elements in the sorted order
Can able to store null objects						Couldn’t store null objects
Performance is fast									Performance is slow

What is mean by Collections in Java?

Ans: Collection is a framework that is designed to store the objects and manipulate the design to store the objects.

What is Synchronization?

Ans: Synchronization makes only one thread to access a block of code at a time. If multiple thread accesses the block of code, then there is a chance for inaccurate results at the end. To avoid this issue, we can provide synchronization for the sensitive block of codes.

The synchronized keyword means that a thread needs a key in order to access the synchronized code.

Locks are per objects. Every Java object has a lock. A lock has only one key. A thread can access a synchronized method only if the thread can get the key to the objects lock.

For this, we use “Synchronized” keyword.

Example:

public class ExampleThread implements Runnable{
 public static void main (String[] args){
 Thread t = new Thread ();
 t.start ();
 } 
 public void run(){
 synchronized(object){
 {
 }
}

What Is Marker Interface? How Is It Used In Java?

Answer : Marker interface is an interface which help us to notify few information to JVM/Compiler. The marker interface does not have any body, it’s a empty interface. Ex. Cloneable, Serialization, etc.

What is meant by Serialization?

Ans: Converting a file into a byte stream is known as Serialization. The objects in the file is converted to the bytes for security purposes. For this, we need to implement java.io.Serializable interface. It has no method to define.

Variables that are marked as transient will not be a part of the serialization. So we can skip the serialization for the variables in the file by using a transient keyword.


Which methods are used during Serialization and Deserialization process?

Ans: ObjectOutputStream and ObjectInputStream classes are higher level java.io. package. We will use them with lower level classes FileOutputStream and FileInputStream.

ObjectOutputStream.writeObject —->Serialize the object and write the serialized object to a file.

ObjectInputStream.readObject —> Reads the file and deserializes the object.

To be serialized, an object must implement the serializable interface. If superclass implements Serializable, then the subclass will automatically be serializable.

Externalizable interface having 2 methods such as readExternal() and writeExternal(). Serializable interface is the super interface for Externalizable interface. 

Methods of object class:
protected Object clone() throws CloneNotSupportedException
      Creates and returns a copy of this object.
public boolean equals(Object obj)
      Indicates whether some other object is "equal to" this one.
protected void finalize() throws Throwable
      Called by the garbage collector on an object when garbage
      collection determines that there are no more references to the object
public final Class getClass()
      Returns the runtime class of an object.
public int hashCode()
      Returns a hash code value for the object.
public String toString()
      Returns a string representation of the object.

public final void notify()
public final void notifyAll()
public final void wait()
public final void wait(long timeout)
public final void wait(long timeout, int nanos)


Why is character array choosen over string?
Because character array saves data in encrypted format which is not readable by human where as string is human readable.

String comparision:
# Output of the following
public class StringComparision{

     public static void main(String []args){
        String s="test";
        String s2="test";
        String s3=new String("test");
        String s4=new String("test");
        String s5=s3.intern();
        String s6=s;
        String s7=new String(s3);
        
        System.out.println("s==s2 : "+s==s2);
        System.out.println("s.equals(s2) : "+s.equals(s2));
        
        System.out.println("s==s3 : "+s==s3);
        System.out.println("s.equals(s3) : " +s.equals(s3));
        
        
        System.out.println("s3==s4: "+s3==s4);
        System.out.println("s3.equals(s4) " +s3.equals(s4));
        
        System.out.println("s==s5 : "+s==s5);
        System.out.println("s.equals(s5) " +s.equals(s5));
        
        System.out.println("s3==s5 : "+s3==s5);
        System.out.println("s3.equals(s5) " +s3.equals(s5));
        
        System.out.println("s==s6 : "+s==s6);
        System.out.println("s.equals(s6) " +s.equals(s6));
        
        System.out.println("s3==s7 : "+s3==s7);
        System.out.println("s3.equals(s7) : "+s3.equals(s7));   
        
     }
}
O/P:
false
s.equals(s2) : true
false
s.equals(s3) : true
false
s3.equals(s4) true
false
s.equals(s5) true
false
s3.equals(s5) true
false
s.equals(s6) true
false
s3.equals(s7) : true

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Design Patterns

1. Creational
2. Functional
3. Behavioral

In core java, there are mainly three types of design patterns, which are further divided into their sub-parts:

1.Creational Design Pattern: Creational design patterns are concerned with the way of creating objects
Factory Pattern: we have a single Factory class that returns the different sub-classes based on the input provided and factory class uses if-else or switch statement to achieve this.
Abstract Factory Pattern: In the Abstract Factory pattern, we get rid of if-else block and have a factory class for each sub-class. Then an Abstract Factory class that will return the sub-class based on the input factory class.
Singleton Pattern:Singleton pattern restricts the instantiation of a class and ensures that only one instance of the class exists in the Java virtual machine. 
Prototype Pattern: Prototype pattern is used when the Object creation is a costly affair and requires a lot of time and resources and you have a similar object already existing. So this pattern provides a mechanism to copy the original object to a new object and then modify it according to our needs. This pattern uses java cloning to copy the object
Builder Pattern.: This pattern was introduced to solve some of the problems with Factory and Abstract Factory design patterns when the Object contains a lot of attributes. Builder pattern solves the issue with large number of optional parameters and inconsistent state by providing a way to build the object step-by-step and provide a method that will actually return the final Object.

2. Structural Design Pattern: Structural patterns provide different ways to create a class structure, for example using inheritance and composition to create a large object from small objects.
Adapter Pattern: The adapter design pattern is one of the structural design patterns and it’s used so that two unrelated interfaces can work together. The object that joins these unrelated interfaces is called an Adapter. As a real-life example, we can think of a mobile charger as an adapter because the mobile battery needs 3 volts to charge but the normal socket produces either 120V (US) or 240V (India). So the mobile charger works as an adapter between the mobile charging socket and the wall socket
Bridge Pattern : When we have interface hierarchies in both interfaces as well as implementations, then bridge design pattern is used to decouple the interfaces from implementation and hiding the implementation details from the client programs
Composite Pattern: Composite pattern is one of the Structural design patterns and is used when we have to represent a part-whole hierarchy. When we need to create a structure in a way that the objects in the structure have to be treated the same way, we can apply the composite design pattern.
Decorator Pattern: The decorator design pattern is used to modify the functionality of an object at runtime. At the same time, other instances of the same class will not be affected by this, so individual object gets the modified behavior. The decorator design pattern is one of the structural design pattern (such as Adapter Pattern, Bridge Pattern, Composite Pattern) and uses abstract classes or interface with the composition to implement
Facade Pattern: Facade Pattern is used to help client applications to easily interact with the system. Suppose we have an application with a set of interfaces to use MySql/Oracle database and to generate different types of reports, such as HTML report, PDF report etc. So we will have a different set of interfaces to work with different types of database. Now a client application can use these interfaces to get the required database connection and generate reports. But when the complexity increases or the interface behavior names are confusing, the client application will find it difficult to manage it. So we can apply Facade pattern here and provide a wrapper interface on top of the existing interface to help client application
Flyweight Pattern: Flyweight design pattern is used when we need to create a lot of Objects of a class. Since every object consumes memory space that can be crucial for low memory devices, such as mobile devices or embedded systems, flyweight design pattern can be applied to reduce the load on memory by sharing objects. String Pool implementation in java is one of the best example of Flyweight pattern implementation
Proxy Pattern: Proxy pattern intent is to “Provide a surrogate or placeholder for another object to control access to it”. The definition itself is very clear and proxy pattern is used when we want to provide controlled access of a functionality.

3. Behavioral Design Pattern
Chain Of Responsibility Pattern
Command Pattern
Interpreter Pattern
Iterator Pattern: Iterator pattern in one of the behavioral pattern and it’s used to provide a standard way to traverse through a group of Objects. Iterator pattern is widely used in Java Collection Framework where Iterator interface provides methods for traversing through a collection
Mediator Pattern
Memento Pattern
Observer Pattern
State Pattern: State design pattern is used when an Object change it’s behavior based on it’s internal state.
Strategy Pattern
Template Pattern
Visitor Pattern: Visitor pattern is used when we have to perform an operation on a group of similar kind of Objects. With the help of visitor pattern, we can move the operational logic from the objects to another class.

Miscellaneous Design Patterns:
DAO Design Pattern
Dependency Injection Pattern
MVC pattern

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

Springboot:
Is a Spring module which provides RAD (Rapid Application Development) feature to Spring framework.
It is used to create stand alone spring based application that you can just run because it needs very little spring configuration


# What does the @SpringBootApplication annotation do internally?

As per the Spring Boot doc, the @SpringBootApplication annotation is equivalent to using @Configuration, @EnableAutoConfiguration, and @ComponentScan with their default attributes.


# What is Spring Actuator? What are its advantages?
It provides many features, i.e. what beans are created, the mapping in the controller, the CPU usage, etc. Automatically gathering and auditing health and metrics can then be applied to your application.

# How to to change the port of Embedded Tomcat server in Spring boot?
You can use the application.properties file to change the port. But you need to mention "server.port" (i.e. server.port=8081). Make sure you have application.properties in your project classpath; 

# What is the difference between RequestMapping and GetMapping?
The @GetMapping is a composed annotation that acts as a shortcut for @RequestMapping(method = RequestMethod.GET). Both these methods support the consumes. The consume options are :

consumes = “text/plain”
consumes = {“text/plain”, “application/*”}
# Starter packages and purpose:
spring-boot-starter: – This is the core starter and includes logging, auto-configuration support, and YAML.
spring-boot-starter-jdbc – This starter is used for HikariCP connection pool with JDBC
spring-boot-starter-web – Is the starter for building web applications, including RESTful, applications using Spring MVC
spring-boot-starter-data-jpa – Is the starter to use Spring Data JPA with Hibernate
spring-boot-starter-security – Is the starter used for Spring Security
spring-boot-starter-aop: This starter is used for aspect-oriented programming with AspectJ and  Spring AOP
spring-boot-starter-test: Is the starter for testing Spring Boot applications

#How to connect Springboot application to database:
configure the database into application properties

spring.datasource.url=jdbc:mysql://localhost:3306/example
spring.datasource.username=root  
spring.datasource.password=edureka  
spring.jpa.hibernate.ddl-auto=create-drop


Annotations:

Spring annotations:
@Autowired to mark a dependency which Spring is going to resolve and inject. We can use this annotation with a constructor, setter, or field injection
@Bean marks a factory method which instantiates a Spring bean
@Qualifier along with @Autowired to provide the bean id or bean name we want to use in ambiguous situations.
@Required on setter methods to mark dependencies that we want to populate through XML
@Value for injecting property values into beans
@Lazy when we want to initialize our bean lazily. By default, Spring creates all singleton beans eagerly at the startup/bootstrapping of the application context.
@Primary : if we mark the most frequently used bean with
@Scope to define the scope of a @Component class or a @Bean definition
@Profile - If we want Spring to use a @Component class or a @Bean method only when a specific profile is active
@Import - We can use specific @Configuration classes without component scanning with this annotation
@PropertySource - With this annotation, we can define property files for application settings:
@PropertySources - We can use this annotation to specify multiple @PropertySource configurations:

SpringMVC annotation:

The @RequestMapping annotation is used to provide routing information. It tells to the Spring that any HTTP request should map to the corresponding method
@RequestMapping it can be configured using:
path, or its aliases, name, and value: which URL the method is mapped to
method: compatible HTTP methods
params: filters requests based on presence, absence, or value of HTTP parameters
headers: filters requests based on presence, absence, or value of HTTP headers
consumes: which media types the method can consume in the HTTP request body
produces: which media types the method can produce in the HTTP response body
@RequestBody – which maps the body of the HTTP request to an object
@PathVariable- This annotation indicates that a method argument is bound to a URI template variable. eg:@RequestMapping("/{id}")
@RequestParam for accessing HTTP request parameters
@ResponseBody, Spring treats the result of the method as the response itself
@ExceptionHandler - With this annotation, we can declare a custom error handler method. Spring calls this method when a request handler method throws any of the specified exceptions.
@ResponseStatus - We can specify the desired HTTP status of the response if we annotate a request handler method with this annotation. We can declare the status code with the code argument, or its alias, the value argument.

Springboot annotations:
The @RestController annotation combines @Controller and @ResponseBody.
The @SpringBootApplication is mark the main class of a Spring Boot application: or bootstrap class
The @EnableAutoConfiguration is used to enable auto-configuration  and component scanning in your project. looks for auto-configuration beans on its classpath and automatically applies them.
The @Value is used to expose the custom application configuration in Spring Boot
@ModelAttribute - With this annotation we can access elements that are already in the model of an MVC @Controller, by providing the model key
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Abstract classes:

Can an abstract class implement an interface?
In Java, an abstract class can implement an interface, and not provide implementations of all of the interface's methods. It is the responsibility of the first concrete class that has that abstract class as an ancestor to implement all of the methods in the interface.

Why does an abstract class have a constructor?
1) Abstract classes have constructors and those constructors are always invoked when a concrete subclass is instantiated. .2) We know constructor are also used to initialize fields of a class. We also know that abstract classes may contain fields and sometimes they need to be initialized somehow by using constructor

Can we create interface object and abstract class?
You cannot create an object of abstract class or interface since they are incomplete class (interface is not even considered as a class.)

Does an abstract class have to have an abstract method?
Yes we can have an abstract class without Abstract Methods as both are independent concepts. Declaring a class abstract means that it can not be instantiated on its own and can only be sub classed. Declaring a method abstract means that Method will be defined in the subclass
