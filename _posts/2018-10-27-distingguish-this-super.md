---
layout: post
title: 区分this和super
date: 2018-10-27 00:00:00 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img:  # Add image post (optional)
tags: [Java, KeyWord] # add tag
---
# this
this是自身的一个对象，代表对象本身，可以理解为对象本身的一个指针
this用法有三种
### 普通的直接引用
this相当于指向当前对象本身

### 形参与成员名字重名，用this区分



	class Person{
	private int age = 10;
	public Person(){
		System.out.println(age);
	}
	public int Getage(int age){
		//this.age = age;
		System.out.println(age);
		return this.age;
		}
	}

	public class Test1 {
	public static void main(String[] args) { 
		Person a = new Person();
		System.out.println(a.Getage(12));
		}
	}



### 引用构造函数

与super类似，见下面

# super

- super可以理解为指向自己超（父）类对象的指针，这个超类是指离自己最近的父类，也就是它所继承的类

### 普通的直接引用

- super相当于指向当前对象的父类，这样可以用super.xxx来引用父类的成员

### 子类成员变量或者方法与父类同名


	class Country {
    String name;
    void value() {
       name = "China";
    }
}
  
	class City extends Country {
    String name;
    void value() {
    name = "Shanghai";
    super.value();      //调用父类的方法
    System.out.println(name);
    System.out.println(super.name);
    }
  
    public static void main(String[] args) {
       City c=new City();
       c.value();
       }
}

### 引用构造函数
- super(参数)参数可以没有，或者是任意个，且super和this语句必须放在构造函数的第一行，下同，
- 调用父类的某一个构造函数(某一个指的是参数相同的构造函数)
- this(参数)调用本类的另一种形式的构造函数
   
'''

	class Person { 
		public static void prt(String s) { 
		System.out.println(s); 
		} 
   
	Person() { 
		prt("父类·无参数构造方法： "+"A Person."); 
		}//构造方法(1) 
    
	Person(String name) { 
		prt("父类·含一个参数的构造方法： "+"A person's name is " + name); 
		}//构造方法(2) 
	} 
    


	public class Chinese extends Person { 
		Chinese() { 
		super(); // 调用父类构造方法（1） 
		prt("子类·调用父类”无参数构造方法“： "+"A chinese coder."); 
		} 
    
	Chinese(String name) { 
		super(name);// 调用父类具有相同形参的构造方法（2） 
		prt("子类·调用父类”含一个参数的构造方法“： "+"his name is " + name); 
		} 
    
	Chinese(String name, int age) { 
		this(name);// 调用具有相同形参的构造方法（3） 
		prt("子类：调用子类具有相同形参的构造方法：his age is " + age); 
		} 
    
	public static void main(String[] args) { 
		Chinese cn = new Chinese(); 
		cn = new Chinese("codersai"); 
		cn = new Chinese("codersai", 18); 
		} 
	}

运行结果：

	父类·无参数构造方法： A Person.
	子类·调用父类”无参数构造方法“： A chinese coder.
	父类·含一个参数的构造方法： A person's name is codersai
	子类·调用父类”含一个参数的构造方法“： his name is codersai
	父类·含一个参数的构造方法： A person's name is codersai
	子类·调用父类”含一个参数的构造方法“： his name is codersai
	子类：调用子类具有相同形参的构造方法：his age is 18

### 从本例可以看到，可以用super和this分别调用父类的构造方法和本类中其他形式的构造方法。

- 例子中Chinese类第三种构造方法调用的是本类中第二种构造方法，而第二种构造方法是调用父类的，因此也要先调用父类的构造方法，再调用本类中第二种，最后是重写第三种构造方法。

## super和this的异同：

- super（参数）：调用基类中的某一个构造函数（应该为构造函数中的第一条语句） 
- this（参数）：调用本类中另一种形成的构造函数（应该为构造函数中的第一条语句）
- super:　它引用当前对象的直接父类中的成员（用来访问直接父类中被隐藏的父类中成员数据或函数，基类与派生类中有相同成员定义时如：super.变量名    super.成员函数据名（实参）
- this：它代表当前对象名（在程序中易产生二义性之处，应使用this来指明当前对象；如果函数的形参与类中的成员数据同名，这时需用this来指明成员变量名）
- 调用super()必须写在子类构造方法的第一行，否则编译不通过。每个子类构造方法的第一条语句，都是隐含地调用super()，如果父类没有这种形式的构造函数，那么在编译的时候就会报错。
- super()和this()类似,区别是，super()从子类中调用父类的构造方法，this()在同一类内调用其它方法。
- super()和this()均需放在构造方法内第一行。
- 尽管可以用this调用一个构造器，但却不能调用两个。
- this和super不能同时出现在一个构造函数里面，因为this必然会调用其它的构造函数，其它的构造函数必然也会有super语句的存在，所以在同一个构造函数里面有相同的语句，就失去了语句的意义，编译器也不会通过。
- this()和super()都指的是对象，所以，均不可以在static环境中使用。包括：static变量,static方法，static语句块。
- 从本质上讲，this是一个指向本对象的指针, 然而super是一个Java关键字。

### 引用

- https://www.cnblogs.com/hasse/p/5023392.html

