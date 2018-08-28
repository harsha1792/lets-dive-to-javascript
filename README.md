# lets-dive-to-javascript

this keyword:

this keyword is used to refer to an object that the function is bound to.
this keyord not only refers to the object but it also contains value of the object.
in stict mode, this hold the value of undefined in global function and in anonymous function that are not bound to any object.
evn though it appears this refer to the object where it is defined,it is not until an object invokes the this function that this is actually assigned a  value.

when we use this in global function, it refers to the global window objectbut not in the strict mode.


# this refers to the global object
  function display() {
    console.log(this === windows);              //true
  }
 
 but in stict mode this will give undefined;
  use strict;
  function display() {
  console.log(this);          //undefined
  }
  
# this refers to the new instance
  When an object is invoked with the 'new' keyword then the function is known as the constructor function and returns a new instance.
  In such cases,this refers to the newly created instance.
   
   function Person(name, age) {
      this.name = name;
      this.age = age;
      
      this.display = function() {
        console.log(`Name: ${this.name} age:${this.age}`);
      }
    }
    var person1 = new Person('jack', 20);
    person1.display();                       //Name: jack age:20
    var person2 =  new Person('jill', 25);  
    person2.display();                      //Name: jill age:25
