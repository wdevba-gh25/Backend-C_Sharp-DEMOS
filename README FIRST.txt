In this solution, I've included exercises that helped me study, analyze and practice the concepts applied in good object-oriented programming practices. I took many examples originally written on JAVA then translated them into C#. You'll need to "set as startup project" the project you want to analyze before running the whole solution. 

I apologize for not translating the entire solution and this document. I've created it from scratch in Spanish back in 2009 when I started to get deeper and deeper into C#. 
Translating ALL today into English would take me forever I really have very little time for that these days. But I think, since the code is in English it would rapidly make sense for anyone reading and studying them.
Some projects have their own separate solution in case you want to run just that project without having to open all the projects. This set of projects has been opened recently with Visual Studio 2022. It should work fine for you:

--- WARNING:

 The projects named "DEFY_" are small challenges I took from the Internet.
 They are not related to the projects named "ED2_".

 ALL THE EXAMPLES named "ED2_" ARE BASED ON JAVA PROGRAMMING LANGUAGE EXAMPLES.
 . HOWEVER, I've TRANSLATED THE SAME EXAMPLES
TO C#, IN THE PROJECTS OF THE "ENLACEDINAMICO"(Dynamic binding) SOLUTION.
The name of the solution is not related to all the projects in the solution.
It is just a solution name that I've choosen because it was the first time.



IT IS IMPORTANT TO STUDY THE CONCEPTS OF THIS EXAMPLE 
SO YOU CAN COMPARE THEM WITH THE SYNTACTIC WAY IN WHICH C# UNDERSTANDS THEM.

THE RELATIONSHIP BETWEEN THE EXAMPLES SHOWN HERE AND THE PROJECTS OF THE
SOLUTION IS 1 TO 1, THROUGH THE FIRST COMMENT THAT APPEARS IN THE
FILE CONTAINING THE EXAMPLE. FOR EXAMPLE:


-------------- THE SAMPLE CODE BELOW IS WRITTEN IN JAVA ---------------
Page 3 contains, in this document, the Inheritance example.
To find its direct translation to c# and thus be able to test it
and debug it in the solution, open any file then press CTRL+F key combination.
Enter the string "Page 3".
Select "Entire Solution" then hit enter.

It will display several results. Find the file where your example is located then double click and you'll be directed to your project of interest.


PREVIOUS TO JAVA SAMPLES:
--------------------
ANNEX: C# MODIFIERS (NOT JAVA)
------------------

 A BRIEF DESCRIPTION WITH EXAMPLES IS PRESENTED BELOW
ABOUT THE MANAGEMENT OF ACCESSIBILITY LEVELS THAT FRAMEWORK OF
.NET OFFERS CLASSES, STRUCTS, INTERFACES AND ITS MEMBERS.

----------------- Page 57 -------------------

INTERNAL

 SEE EXAMPLE IN SOLUTION "DYNAMIC LINK",
VISUAL STUDIO 2022.

----------------- Page 58 -------------------

PROTECTED INTERNAL

SEE EXAMPLE IN SOLUTION "DYNAMIC LINK",
VISUAL STUDIO 2022.
----------------- Page 59 -------------------
SEALED



SEE EXAMPLE IN SOLUTION "DYNAMIC LINK",
VISUAL STUDIO 2022.
----------------- Page 60 -------------------
STRUCT



SEE EXAMPLE IN SOLUTION "DYNAMIC LINK",
VISUAL STUDIO 2022.
----------------- Page 61 -------------------
STATIC



SEE EXAMPLE IN SOLUTION "DYNAMIC LINK",
VISUAL STUDIO 2022.
----------------- Page 62 -------------------
OUT




SEE EXAMPLE IN SOLUTION "DYNAMIC LINK",
VISUAL STUDIO 2022.
----------------- Page 63 -------------------
REF


SEE EXAMPLE IN SOLUTION "DYNAMIC LINK",
VISUAL STUDIO 2022.
----------------- Page 64 -------------------
PARTIAL


SEE EXAMPLE IN SOLUTION "DYNAMIC LINK",
VISUAL STUDIO 2022.
----------------- Page 65 -------------------
READONLY



SEE EXAMPLE IN SOLUTION "DYNAMIC LINK",
VISUAL STUDIO 2022.

----------------- Page 66 -------------------
CONST



SEE EXAMPLE IN SOLUTION "DYNAMIC LINK"(EnlaceDinamico),
VISUAL STUDIO 2022 HERE BELOW (JAVA LANGUAGE):

----------------- Page 1 -------------------
Herencia y Enlace Dinámico
----------------- Page 2 -------------------
Herencia
----------------- Page 3 -------------------
Herencia
class A {
  int i, j;
  void mostrarij() {
    System.out.println(“i y j: “ + i + “ “ + j);
  }
}

class B extends A {
  int k;
  void mostrark() {
    System.out.println(“k: “ + k);
  }
  void sum() {
    System.out.println(“i+j+k: “ + i+j+k);
  }
}
----------------- Page 4 -------------------
class SimpleHerencia {
  public static void main(String args[]) {
    A superOb = new A();
    B subOb = new B();
    SuperOb.i = 10;
    SuperOb.j = 20;
    System.out.println(“Contenido de superOb: “);
    SuperOb.mostrarij();
    System.out.println();
    SubOb.i = 7;
    SubOb.j = 8;
    SubOb.k = 9;
    System.out.println(“Contenido de subOb: “);
    SuperOb.mostrarij();
    SuperOb.mostrark();
    System.out.println();
    System.out.println(“i+j+k en subOb: “);
    SubOb.sum();
  }
}
----------------- Page 5 -------------------
Acceso a miembros y herencia
Una subclase no puede acceder a miembros de la
superclase que han sido declarados como privados
(private).
----------------- Page 6 -------------------
class A {
  int i; // por defecto es pública
  private int j; // privada a A
  void establecerij(int x, int y) {
    i = x;
    j = y;
  }
}
class B extends A {
  int total;
  void sum() {
    total = i + j;
  }
}
class Acceso {
  public static void main(String args[]) {
    B subOb = new B();
    SubOb.establecerij(10, 12);
    SubOb.sum();
    System.out.println(“Total: “ + subOb.total);
  }
}
----------------- Page 7 -------------------
class Caja {
  double ancho;
  double alto;
  double prof;
  Caja(Caja ob) {
    ancho = ob.ancho; alto = ob.alto; prof = ob.prof;
  }
  Caja() {
    ancho = alto = prof = -1;
  }
  Caja(double w, double h, double d) {
    ancho = w; alto = h; prof = d;
  }
  Caja(double longi) {
    ancho = alto = prof = longi;
  }
  double volumen() {
    return ancho * alto * prof;
  }
}

----------------- Page 8 -------------------
class WeightBox extends Box {
  double weight;
  BoxWeight(double w,double h,double d,double p) {
    width = w;
    height = h;
    depth = d;
    weight = p;
  }
}
----------------- Page 9 -------------------
Important!:
A superclass variable can be
assign a reference to any subclass
derived from said superclass.
----------------- Page 10 -------------------
class RefDemo {
  public static void main(String args[]) {
    BoxWeight boxp = new BoxWeight(3, 5, 7, 8.37);
    Box box;
    double vol;
    vol = boxp.volume();
    System.out.println(“The volume of boxp is “ +
                        vol);
    System.out.println(“The weight of boxp is “ +
                        boxp.weight);
    System.out.println();
    box = boxp;
    vol = box.volume();
    System.out.println(“The cash volume is “ +
                        vol);
    System.out.println(“The box weight is “ +
                        box.weight);
  }
}
----------------- Page 11 -------------------
box (box)
broad
high
depth

boxp (BoxWeight)Object BoxWeight
weight

----------------- Page 12 -------------------
The super method
üAccess to the superclass constructor.
üAccess to a member of the hidden superclass
in the subclass.
----------------- Page 13 -------------------
Builder access
class WeightBox extends Box {
  double weight;
  BoxWeight(double w,double h,double d,double p) {
    width = w; height = h; depth = d; weight = p;
  }
  BoxWeight(CashWeight ob) {
    width = ob.width; height = ob.height; prof = ob.prof;
    weight = ob.weight;
  }
}
the following would be put:
class WeightBox extends Box {
  double weight;
  BoxWeight(double w,double h,double d,double p) {
    super(w, h, d);
    weight = p;
  }
  BoxWeight(CashWeight ob) {
    super(ob);
    weight = ob.weight;
  }
}
----------------- Page 14 -------------------
super, if used, must be the first instruction
to be used in the subclass constructor:
Constructor( arguments ... ) {
  super(...);
  . . .
}
----------------- Page 15 -------------------
Access to hidden members
class A {
  int i;
}
class B extends A {
  int i; //this i hides the i of A
  B(int a, int b) {
    super.i = a; // idea
   i = b; // i of B
  }
  void show() {
    System.out.println(“superclass i: “ +
                        super.i);
    System.out.println(“subclass i: “ + i);
  }
}
class UsaSuper {
  public static void main(String args[]) {
    B subOb = new B(1, 2);
    SubOb.show();
  }
}
Exit:
i of superclass: 1
subclass i: 2
----------------- Page 16 -------------------
Constructor Execution Order
class A {
  TO() {
    System.out.println(“In the constructor of A.”);
  }
}
class B extends A {
  B() {
    System.out.println(“In the constructor of B.”);
  }
}
class C extends B {
  C() {
    System.out.println(“In the C constructor.”);
  }
}
class ConsCalls {
  public static void main(String args[]) {
    C c = new C();
  }
}
Exit:
In the constructor of A.
In the constructor of B.
In the C constructor.

----------------- Page 17 -------------------
Method override
class A {
  int i, j;
  A(int a, int b) {
    i = a; j = b;
  }
  void show() {
    System.out.println(“i and j: “ + i + “ “ + j);
  }
}
class B extends A {
  int k;
  B(int a, int b, int c) {
    super(a, b);
    k = c;
  }
  void show() {
    System.out.println(“k: “ + k);
  }
}
class Override {
  public static void main(String args[]) {
    B subOb = new B(1, 2, 3);
    SubOb.show();
  }
}
Output:k:3
----------------- Page 18 -------------------
If you want to access the version of the show superclass.
void show() {
  super.show();
  System.out.println(“k: “ + k);
}
Exit:
i and j: 1 2
k:3
----------------- Page 19 -------------------
Dynamic selection of method or
Dynamic Link
----------------- Page 20 -------------------
class A {
  void callme() {
    System.out.println(“Call \”callme\” inside A”);
  }
}
class B extends A {
  void callme() {
    System.out.println(“Call \”call me\” inside B”);
  }
}
class C extends A {
  void callme() {
    System.out.println(“Call \”callme\” inside C”);
  }
}
class DynamicSelection {
  public static void main(String args[]) {
    A a = new A();
    B b = new B();
    C c = new C();
    A r = a;
    r.callme();
    r = b;
    r.callme();
    r = c;
    r.callme();
  }
}

----------------- Page 21 -------------------
Exit:
Call ”call me” inside A
Call ”call me” inside B
Call ”call me” inside C
----------------- Page 22 -------------------
Advantages of Dynamic Link
ü Method overriding allows Java to support polymorphism
at runtime.
ü Polymorphism is essential in OO programming for a simple
reason:
Allows a general class to specify methods that will be
common to all its derived classes, allowing them to define the
specific implementation of any of these methods.
• This form of dynamic polymorphism during execution is one of
the most powerful mechanisms that OO design offers to support:
ü code reuse and
ü robustness.
• The ability of existing code libraries to call
to methods of new instances of classes without recompiling them, but
while maintaining the abstract and clean interface, it is a tool
profoundly powerful.
----------------- Page 23 -------------------
class Figure
{
  double dim1;
  double dim2;

  Figure(double a, double b)
  {
    dim1 = a;
    dim2 = b;
  }

  doublearea()
  {
    System.out.println(“Figure Area not defined.”);
    double 0;
  }
}

class Rectangle extends Figure
{
  Rectangle(double a, double b)
  {
    super(a, b);
  }

  doublearea()
  {
    System.out.println(“Within Rectang area.”);
    return dim1 * dim2;
  }
}

class Triangle extends Figure {
  Triangle(double a, double b) { super(a, b); }
  double area() {
    System.out.println(“Within Triang area.”);
    return dim1 * dim2 / 2;
  }
}

----------------- Page 24 -------------------
class SearchAreas {
  public static void main(String args[]) {
    Figure f = new Figure(10, 10);
    Rectangle r = new Rectangle(9, 5);
    Triangle t = new Triangle(10, 8);

    Figure figref = r;
    System.out.println(“Area = “ + figref.area());
    figref = t;
    System.out.println(“Area = “ + figref.area());
    figref = f;
    System.out.println(“Area = “ + figref.area());
  }
}
Within Rectang area.
Area = 45
Within Triang area.
Area = 40
Undefined Figure Area
Area = 0
----------------- Page 25 -------------------
Type conversion between classes
• Type conversions can only occur between classes related by inheritance.
The following is an error:
class A { int a; }
class B { int b; }
public class MainClass {
  public static void main(String args[]) {
    A a = new A();
    Bb;
    b = (B)a;
  }
}
----------------- Page 26 -------------------
Type conversion between classes
• Type conversions can only occur between classes related by inheritance.
The following is possible because the types are compatible.
class A { int a; }
class B extends A { int b; }
public class MainClass {
  public static void main(String args[]) {
    A a = new A();
    Bb;
    b = (B)a;
  }
}
----------------- Page 27 -------------------
Type conversion between classes
• Type conversions can only occur between classes related by inheritance.
However, through b you do not have access to all the variables of class B
but to those of A. The following is wrong.
class A { int a; }
class B extends A { int b; }
public class MainClass {
  public static void main(String args[]) {
    A a = new A();
    Bb;
    b = (B)a;
    b.b = 3;
  }
}
----------------- Page 28 -------------------
Type conversion between classes
• The following is correct because the dynamic type of the object is class B.
class A { int a; }
class B extends A { int b; }
public class MainClass {
  public static void main(String args[]) {
    A a = new B();
    Bb;
    b = (B)a;
    b.b = 3;
  }
}

----------------- Page 29 -------------------
Type conversion between classes
• The same rules are followed for the methods.
• If the method is overridden, the method is always executed.
dynamic type method regardless of whether
whether type conversion exists or not.
----------------- Page 30 -------------------
Abstract classes (abstract)
• Objective: Declare the structure of an abstraction without
   provide an implementation for each method.

• The abstract superclass determines the nature of
  the methods that the subclasses must implement.

EXAMPLE:

 abstract <type> <name>(parameter_list);

• Characteristics:
ü Any class that contains one or more methods
  abstracts must also be declared as abstract.

ü There cannot be objects (instances) of a
  abstract class.

ü You cannot declare abstract constructors or
  static abstract methods.

• STATEMENT 6
  Any subclass of an abstract class must
  implement all abstract methods of the
  superclass or also be declared as abstract.

----------------- Page 31 -------------------
abstract class A {
  abstract void callme();
 void callmetalso() {
    System.out.println(“This is a concrete method”);
  }
}
class B extends A {
  void callme() {
    System.out.println(“Implementation of call me in
B”);
  }
}
----------------- Page 32 -------------------
abstract class Figure {
  double dim1;
  double dim2;
  Figure(double a, double b) {dim1 = a; dim2 = b;}
  abstract doublearea();
}
class Rectangle extends Figure {
  Rectangle(double a, double b) { super(a, b); }
  double area() {
    System.out.println(“Within Rectang area.”);
    return dim1 * dim2;
  }
}
class Triangle extends Figure {
  Triangle(double a, double b) { super(a, b); }
  double area() {
    System.out.println(“Within Triang area.”);
    return dim1 * dim2 / 2;
  }
}
----------------- Page 33 -------------------
class SearchAreas {
  public static void main(String args[]) {
    // Figure f = new Figure(10, 10);
    Rectangle r = new Rectangle(9, 5);
    Triangle t = new Triangle(10, 8);
    figure figref;
    figref = r;
    System.out.println(“Area = “ + figref.area());
    figref = t;
    System.out.println(“Area = “ + figref.area());
    figref = f;
    System.out.println(“Area = “ + figref.area());
  }
}

----------------- Page 34 -------------------
Using final with inheritance

The three uses of ending:
– Creation of the equivalent of a constant.
– Avoid overwriting (they can provide an improvement in the
performance).
class A {
  final void math() {
    System.out.println(“This is a final method”);
  }
}
class B extends A {
  void math(){ //ERROR! Cannot be overwritten.
    System.out.println(“Not correct”);
  }
}
– Avoid inheritance.
final class A {
  . . .
}
class B extends A { // ERROR!
  . . .
}


----------------- Page 36 -------------------

Interfaces (FOR THE JAVA LANGUAGE)

----------------- Page 37 -------------------

or
You can totally abstract the interface of a class from its
implementation, that is, specifying what a class does but not how it does it
does.

or
Interfaces do not have instance variables and methods do not have
body (abstract).

or
Any number of classes can implement an interface.

or
A class can implement any number of interfaces.

or
Interfaces are designed to support method resolution
(dynamic link) during execution without the need for
be carried out between classes related by inheritance.

or
Interfaces are in a different hierarchy than the class hierarchy,
so it is possible that several classes that do not have the slightest
relationship in terms of inheritance implement the same interface.

----------------- Page 38 -------------------

Definition of an interface

access interface name {
  return_type method1(parameter_list);
  return_type method2(parameter_list);
  type var_final1 = value;
  type var_final2 = value;
  . . .
}

Access is public or without modifier.
Variables are implicitly final and static and must be
initialized.

IN C SHARP:
FINAL IS 'SEALED or CONST'.
THIS IS DUE TO THE DEFINITION OF INTERFACE.
IT IS NOT REALLY A GOOD PRACTICE TO USE VARIABLES IN INTERFACES,
SINCE THE COMPILER WILL AUTOMATICALLY MARK IT AS 'SEALED STATIC'
AND THEREFORE THE 'VARIABLE' CANNOT BE MODIFIED BY ANY CLASS THAT
IMPLEMENT THE INTERFACE. IT WILL END UP BEING NO MORE THAN A CONSTANT,
FOR PRACTICAL PURPOSES

----------------- Page 39 -------------------

Implementation of an interface

access class class_name [extends superclass]
          [implements interface1[, interface2...]]
{
  //class body
}

or
Access is public or not used.

ü STATEMENT 2:
If a class implements two interfaces that declare the same method,
clients will use the same method.

HOWEVER, SUCH PRACTICE IS NOT RECOMMENDED, ACCORDING TO THE
SOLID PRINCIPLES WE MUST DO EVERYTHING POSSIBLE TO SEPARATE RESPONSIBILITIES
AND MAKE LITTLE DEPENDENCE BETWEEN CLASSES.

or
Methods that implement an interface must be declared as
public.

----------------- Page 40 -------------------

//Interface declaration

Callback interface
{
  void callback(int param);
}


//Interface implementation
class Client implements Callback
{
  public void callback(int p)
  {
    System.out.println(“callback called with “+p);
  }
}
----------------- Page 41 -------------------

References to interfaces and dynamic binding
with interfaces

or
Any instance of a class that implements the declared interface
can be stored in a variable of this type.

or
The call to a method through these variables will be made based on
to the instance of the interface that is being referenced (link
dynamic with interfaces).

class TestIface
{
  public static void main(String args[])
  {
    Callback c = new Client();
    c.callback(42);
  }
}

• STATEMENT 3
Using c, only the callback method of the class can be accessed
Client and not to the rest of the elements that may have been defined
in the same class.

• STATEMENT 4
A class that includes an interface and does not implement all methods
defined by the interface has to be declared as abstract.

SIMILARITY WITH STATEMENT 6 OF Page 30

----------------- Page 42 -------------------

//Interface declaration

Callback interface
{
  void callback(int param);
}

//Interface implementation
class Client implements Callback
{
  public void callback(int p)
  {
    System.out.println(“callback called with “ + p);
  }
}

class OtherCustomer implements Callback
{
  public void callback(int p)
  {
    System.out.println(“Another version of “ + “callback”);
    System.out.println(“The square of p is ” + (p*p));
  }
}

class TestIface2
{
  public static void main(String args[])
  {
    Callback c = new Client();
    AnotherCustomer oc = new OtherCustomer();
    c.callback(42);
    c = ob;
    c.callback(42);
  }
}

----------------- Page 43 -------------------
Exit:
callback called with 42
Another version of callback
The square of p is 1764

----------------- Page 44 -------------------

IntStack interface
{
  void put(int elem);
  int remove();
}

classFixedStack implementsStackInt
{
  private int stack[];
  private int n;
  FixedStack(int size)
  {
    stack = new int[size];
    n = -1;
  }

  public void put(int elem)
  {
    if(n==stack.length-1)
      System.out.println(“The stack is full”);
    else
      stack[++n] = elem;
  }

  public int remove()
  {
    if(n<0)
    {
      System.out.println(“The stack is empty”);
      return 0;
    } else
      return stack[n—];
  }

}
----------------- Page 45 -------------------
class PilaDin implements IntPila
{
  private int stack[];
  private int n;
  PilaDin(int size)
  {
    stack = new int[size];
    n = -1;
  }

  public void put(int elem)
  {
    if(n==stack.length-1)
    {
      int temp[] = new int[stack.length*2];
      for(int i=0; i<stack.length; i++)
        temp[i] = stack[i];
      stack = temp;
    }
    stack[++n] = elem;
  }

  public int remove()
  {
    if(n<0)
    {
      System.out.println(“The stack is empty”);
      return 0;
    } else
      return stack[n—];
  }
}

----------------- Page 46 -------------------

Using an IntPila type variable you can
use the put and remove methods of a
fixed stack or a dynamic stack depending on what
instance refers to the variable at a time
given.

----------------- Page 47 -------------------
Shared constants

interface SharedConsts
{
  int NOT = 0;
  int IF = 1;
  int MAY = 2;
  int LATE = 3;
  int SOON = 4;
  int NEVER = 5;
}
----------------- Page 48 -------------------

Inheritance in Interfaces

interface A
{
  void meth1();
  void meth2();
}

interface B extends A
{
  void meth3();
}

class My implements class B
{
  public void meth1()
  {
    System.out.println(“Implement meth1”);
  }

  public void meth2()
  {
    System.out.println(“Implement meth2”);
  }

  public void meth3()
  {
    System.out.println(“Implement meth3”);
  }
}
class IFExtend
{
  public static void main(String args[])
  {
    Micalse ob = new Micalse();
    ob.meth1();
    ob.meth2();
    ob.meth3();
  }
}

----------------- Page 49 -------------------

Packages and access control
 SEE DOCUMENTS:
  DLL ANALYSIS NAMESPACES AND USING.txt
  Namespace vs Packages.xls

----------------- Page 50 -------------------

Definition of a package

•
Packages are a mechanism for
partition class namespace more
manageable by restricting their visibility.

•
Definition of a package:
package package;


•

As the first instruction of a source file
Java.


•

Any class that is defined in a source file
Java with this statement belongs to the paq package.

----------------- Page 51 -------------------

•
All classes must be associated with a package, otherwise
includes the
package statement are associated with the default package (without a name).



•
Java uses the file system to store packages.
A
class (.class file) that is inside the Mypackage package must
be inside the MyPackage directory.



•
The package statement with the same package name can
be included in more than one source file (this is usually normal in
large applications).


•
There can be a hierarchy of several levels of packages:
package paq1[.paq2[.paq3]];


•
This package hierarchy must be reflected in the file system.
package java.awt.image; //In java\awt\image


----------------- Page 52 -------------------

The CLASSPATH environment variable

•
The specific location that the Java compiler
considered as the root of any package hierarchy is
controlled by the CLASSPATH variable.


•
For Java to find the classes to execute, the variable
CLASSPATH must contain the list of directories where you have
to search for the classes to execute.


----------------- Page 53 -------------------

Example

or
We have the test package.


or
In the test directory we have the file
TestPackage.java with the TestPackage class


or
We compile PackageTest.java with test being the directory
current generating PackageTest.class in the directory
proof.


or
If you try to run javaTestPackage, you will get an error
because that class is in a package called test and
We cannot refer to her simply by her name.


or
It is possible to refer to any class of any package by listing
your dot-separated package hierarchy:
java test.TestPackage


or
The above example will still fail with the statement
because the CLASSPATH variable must contain the list of
proper directories and the test directory is not one of them.


ü CLASSPATH usually has something like .;C:\java\classes

----------------- Page 54 -------------------

Access control

•
Packages add another dimension to access control.


•
Java Visibility Categories:
– Subclasses of the same package
– Not subclasses of the same package
– Subclasses in different packages
– Classes that are neither in the same package nor in subclasses


•
Ideas:
– Something declared as public can be accessed from any site.
– Anything declared private is not visible from outside the
class.
– Anything declared without a modifier is visible within the same
package.
– With protected, visibility is given from the subclasses wherever they are.


----------------- Page 55 -------------------

Access control

----------------- Page 56 -------------------


The import statement

•
The import statement allows you to reference other classes
packages without needing to specify the entire hierarchy
import package1[.package2].(class_name|*);


•
 The standard Java classes are in the java.


•
 The basic language functions are in java.lang.
