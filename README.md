# Java实验4
## 实验内容
某学校为了给学生提供勤工俭学机会，也减轻授课教师的部分压力，准许博士研究生参与课程的助教工作。此时，该博士研究生有双重身份：学生和助教教师。 

1.设计两个管理接口：学生管理接口和教师管理接口。学生接口必须包括缴纳学费、查学费的方法；教师接口包括发放薪水和查询薪水的方法。  

2.设计博士研究生类，实现上述的两个接口，该博士研究生应具有姓名、性别、年龄、每学期学费、每月薪水等属性。（其他属性及方法，可自行发挥）  

3.编写测试类，并实例化至少两名博士研究生，统计他们的年收入和学费。根据两者之差，算出每名博士研究生的年应纳税金额（国家最新工资纳税标准，请自行检索）。
## 实验要求
1.在博士研究生类中实现各个接口定义的抽象方法;

2.对年学费和年收入进行统计，用收入减去学费，求得纳税额；

3.国家最新纳税标准（系数），属于某一时期的特定固定值，与实例化对象没有关系，考虑如何用static  final修饰定义。

4.实例化研究生类时，可采用运行时通过main方法的参数args一次性赋值，也可采用Scanner类实现运行时交互式输入。

5.根据输入情况，要在程序中做异常处理。
## 核心代码
    public interface StuManage {
	    void payTuitionFee();                //定义缴纳学费方法
	    void inquireTuitionFee();            

    }
>定义接口，定义方法

    public class Dc implements StuManage,TeaManage {
	    int number,age;                      //定义整型变量，学号、年龄
	    String name,sex,major;               //定义字符型变量姓名、性别、专业
    }
>定义Dc类实现接口，定义学生的基本属性

    public void payTuitionFee(){         //重写缴纳学费方法
		    int b1,b2;
		    int x = 16;                      //假设需要纳税16元
		    b1 = f1-p1-x;
		    b2 = f2-p2-x;
		    System.out.println("已成功缴纳学费！纳税后工资剩余:"+"\n"+"小明:"+b1+"\t"+"小红:"+b2);
	  }
    public void inquireTuitionFee(){
    	  System.out.println("计算机专业:————"+"\t"+"学费"+a1+"（每学期）"+"\t"+"\t"+"应缴纳:"+p1+"\n"+
		                   "美术学专业:————"+"\t"+"学费"+a2+"（每学期）"+"\t"+"\t"+"应缴纳:"+p2);
	  }
    public void provideSalary() {
    	
    	
    }
    public void inquireSalary() {
    	  System.out.println("计算机专业:————"+"\t"+"月薪"+s1+"\t"+"\t"+"年收入:"+f1+"\n"+
    			           "美术学专业:————"+"\t"+"月薪"+s2+"\t"+"\t"+"年收入:"+f2);
    }
>重写方法，给出方法体

    public class Test extends Dc {
>继承Dc类的方法

    while(true) {                       //循环执行开关语句
			try {                           //异常处理
				System.out.println("请输入接下来的操作----查询薪水:1  查询学费:2  缴纳学费:3  结束操作:4");
				int i;
				Scanner input=new Scanner(System.in);
				i=input.nextInt();
				switch(i) {
				case 1:
					dc.inquireSalary();
					break;
				case 2:
					dc.inquireTuitionFee();
					break;
				case 3:
					dc.payTuitionFee();
					break;
				case 4:
					System.out.println("程序结束");
					System.exit(0);
				default :
					System.out.println("没有此选项！");
			
				}
			}
			catch(Exception e) {
				System.out.println("输入格式错误！");
			}
		}
>用while语句使switch语句循环运行，try语句检测用户输入的值是否异常，格式错误则报错。
## 实验运行结果
![实验结果]()
## 实验感想
通过这次实验我熟练的掌握了接口的使用方法，学会了用try-catch语句做异常处理。  
一开始做异常处理功能时总是有问题，不能正常报错，通过看书仔细地学习了它的用法，解决了问题。
