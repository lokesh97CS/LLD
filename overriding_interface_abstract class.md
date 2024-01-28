# Over loading :
In a class , we can have multiple functions with same name but different signature<br>
Signature comprises of {function name, params}<br>
```
These throw compile time error 
void ball(string s){}
int ball (string s){}
```
# Method over riding:
Child class can over ride parent class<br>
```
class Parent{
void hello(){
  cout<< "class Parent"<<endl;
    }
  }
class Child extends Parent{

void hello (){cout<<"hello child"<<endl;}

  }
// we can create independent objects like

Parent A = new Parent();A.hello();
Child B =new Child();B.hello();

// But this is suggested

Parent C = new child();C.hello();

//compiler always binds based on data type, as Parent is data type it will check whethet it has hello method or no
//But in run time, actual object is child , the child hello function  will be called , if not present parant hello function will be called

// common use case is having one 
List<Parent> children ={child1 =new child(),child2 =new child(),child3 =new child()}
for(Parent c:children){
  cout<<c.hello();
  }
```
# in c++ , with virtual keyword
```
d= new deriverd();// 
base *b = &d;
b.hello()// it will case call base class function not children , compiler will calls only  based on (data type )method
 so need to add virtual befor the overidden function in base class

this works ased on vtable and vptr
```
#Interfaces
want code to be loosely coupled <br>
OInterface can thave attribu6es <br>
from interfaces we create classes, interfaces will have only methods names but no definition , these definitions implemented in class <br>
```
interface stack{
void push()
void pop()
void isempty()
}
```
```
class ArraystacK implements stack{
}
class linkedlistSTACK implements stack{
}
// class can implements many interfaces
//Even though they have common methods, we define function define only once in class
class Loki implements stackA, stackB{
}
```
#Abstract class
Claas can become abstract with/without having abstract method <br>
 if you make abstract class , it means we can't implement object of it <br>
 if you have abstract method, class must be abstract type <br>
 ```
abstract Animal{
abstract void eat() {}
}
Class Dog extends Animal{
void eat(){}
}

Animal a() //xxxxxx cannot be create das it is abstract
Animal a = new Dog() // This is valid
```
 if the method is abstract then child class must have over ridden method , otherwise compiler will throw error <br>
 if dont want to have overidden method, make child class also as abstract <br>
in java  ,no multiple inheritance<br>
in c++, multiple inheritance cause diamond problem<br>
