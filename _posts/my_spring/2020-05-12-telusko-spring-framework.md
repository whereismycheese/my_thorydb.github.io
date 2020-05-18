---
layout: post
title:  "telusko spring tutorial"
subtitle:   "-"
categories: spring
tags: telusko spring tutorial
comments: true
header-img: img/spring/telusko.jpg
---

:point_right:1. Introduction to Spring – 00:05

>스프링은 여러 모듈을 제공해준다.. 따라서 개발이 편리하다!

why do we need SPRING?  
spring provide various modules!

>어떤 편리함이 있는가?

- common issue: dependencies -> spring provides IoC  
- web framework: MVC -> spring has its own MVC module  
- connect to database -> spring has its own database module  

<br>
:point_right:2. What is Dependency Injection ? – 01:41

>스프링의 특징(feature) 중 하나, Dependency Injection은 무엇이고 왜 필요한가?

DI is a important design pattern concept..why?  
- we do not want our software to be `tightly coupled`  
- easier `unit testing`

```java
// new를 사용한 자바코드
class Laptop {
  HardDrive obj1 = new HitachiHD();
  //HitachiHD -> samsungHD로 바꾸고 싶다면?  
}
```
the moment you say `new`,  
you are going for `tight coupling`..

we use, `dependency injection spring container`  
: they create objects and inject those to my class.. `loose coupling btw objects!`

inject what to whome? mention it in `configuration file`
- xml file configuration(edit in the future, loose couple!)  
- spring boot: java configuration

<br>
:point_right:3. Introduction to Maven  – 09:46  
:point_right:4. Maven Practical – 17:13

>메이븐은 개발에 필요한 다양한 라이브러리들을 다운받고 관리하는 역할을 한다

Maven is..  
- build tool(compile my file)  
- dependency management  
- getting those jar files I need  

`"Hey! maven Repository, I want this dependency!"`  
specify it here `pom.xml`  

go to `mvnrepository.com  `  
and search for library you want!  

whenever working with MAVEN,    
make sure the `internet connection!  `

Local Repository(my pc) & Remote Repository  

<br>
:point_right:5. ApplicationContext – 29:04
:point_right:6. Spring.xml – 41:39

>스프링의 DI 덕분에..  
자바 코딩으로는 비즈니스 로직을 구현하는데에만 집중할 수 있다.  

나중에 세부적인 내용(예를들어, vehicle을 car로 할 것인지 bike로 할 것인지와 같은)을 수정할 일이 있다면 자바코드는 그대로두고,  
설정문서(configuration file)만 수정하면 된다.  
즉 DI 덕분에 코드를 re-compile할 일이 줄어들고  
object들간의 tight coupling문제를 해결할 수 있었다!  

- Vehicle.java (interface)
- Car.java (class)
- Bike.java (class)
- App.java (main class)
- spring.xml (vehicle object을 생성하고 App.java에 inject한다)

```java
public class App {
  public static void main(String[] args) {
    ApplicationContext context = new ClassPathXmlApplicationContext("spring.xml");

    Vehicle obj = (Vehicle)context.getBean("vehicle");
    //where this 'vehicle' keword come from? - spring.xml
    obj.drive();
  }
}
```
App.java에서 사용한 `vehicle이란 bean은 어디서 온것인가?`
spring.xml파일에서 vehicle이란 id를 가진 bean이 준비되어있다!
또한 `그 vehicle이란 id를 가진 bean의 진짜 존재는 class`에 적혀있다  

```xml
<beans>
  <!-- class=[from which class we wnana create this bean] -->
  <bean id="vehicle" class="com.navin.Telusko.Bike"></bean>
  <!-- specify what vehicle you want here! -->
</beans>
```

```java
// abstraction - create interface
public interface Vehicle {
  void drive();
}
```

```java
public class Car implements Vehicle {
  public void drive() {
    System.out.println("부릉부릉");
  }
}
```

```java
public class Bike implements Vehicle{
  public void drive() {
    System.out.println("따릉따릉");
  }
}
```
<br><br>

>자바 클래스를 @Component화 해서 App.java메인코드에서 new를 사용하지 않는 방법도 있다.  

이때는 xml 설정파일에(context:componenet-scan tag) 어떤 패키지에 있는 클래스들이 @Component화 되어 사용될 것인지를 명시해주어야 한다.  

:point_right:7. Annotation Based Configuration – 45:59

```java
public class App {
  public static void main(String[] args) {
    ApplicationContext context = new ClassPathXmlApplicationContext("spring.xml");

    Vehicle obj = (Vehicle)context.getBean("car"); // specify what vehicle you want here!
    obj.drive();
  }
}
```

```java
@Component
public class Car implements Vehicle {
  public void drive() {
    System.out.println("부릉부릉");
  }
}
```

```xml
<!-- spring.xml -->
<beans>
  <context:component-scan base-package="com.navin.Telusko"></context:component-scan>
  <!-- <bean id="vehicle" class="com.navin.Telusko.Bike"></bean> -->
</beans>
```


<br>
>bean으로 등록시킨 클래스의 변수는 property태그로 설정한다  

:point_right:8. Bean Property – 52:25

```java
public class Tyre {
  private String brand;

  public String getBrand() {
    return brand;
  }

  public void setBrand(String brand) {
    this.brand = brand;
  }

  @Override
  public String toString() {
    return "Tyre [brand=]" + brand + "]";
  }
}
```

```java
public class App {
  public static void main(String[] args) {
    ApplicationContext context = new ClassPathXmlApplicationContext("spring.xml");

    Tyre t = (Tyre) context.getBean("tyre");
    System.out.println(t);
  }
}
```

```xml
<!-- spring.xml -->
<beans [custom tags definition]>
  <context:component-scan base-package="com.navin.Telusko"></context:component-scan>
  <!-- <bean id="vehicle" class="com.navin.Telusko.Bike"></bean> -->

  <bean id="tyre" class="com.navin.Telusko.Tyre">
    <property name="brand" value="MRF"></property>
  </bean>
</beans>
```

<br>
>propert태그 사용 대신 constructor-arg태그를 활용해서.. 클래스가 가진 변수값을 설정할 수도 있다!

:point_right:9. Constructor Injection – 57:29
we can assign value using `setter injection(Bean property tag)`
or using `Constructor injection(constructor-arg tag)`  

```java
public class Tyre {
  private String brand;

  //how to set variable brand? - Constructor injection
  public Tyre(String brand) {
    super();
    this.brand = brand;
  }

  public String getBrand() {
    return brand;
  }

  //how to set variable brand? - setter injection
  public void setBrand(String brand) {
    this.brand = brand;
  }

  @Override
  public String toString() {
    return "Tyre [brand=]" + brand + "]";
  }
}
```

```xml
<!-- spring.xml -->
<beans [custom tags definition]>
  <context:component-scan base-package="com.navin.Telusko"></context:component-scan>
  <!-- <bean id="vehicle" class="com.navin.Telusko.Bike"></bean> -->

  <bean id="tyre" class="com.navin.Telusko.Tyre">
    <!-- <property name="brand" value="MRF"></property> -->
    <constructor-arg value="MRF"></constructor-arg>
  </bean>
</beans>
```


<br>
> Car bean이 Tyre bean을 자바코드상에서 사용해야 한다면..  
@Autowired 어노테이션으로 Tyre bean을 연결시켜 주어야 한다  

:point_right:10. Autowired Annotation – 59:52

```java
public class App {
  public static void main(String[] args) {
    ApplicationContext context = new ClassPathXmlApplicationContext("spring.xml");

    Car obj = (Car)context.getBean("car"); //@Component
    obj.drive();
  }
}
```

```java
@Component //Annotation based configuration
public class Car implements Vehicle {
  @Autowired //Annotation based configuration
  private Tyre tyre;

  public Tyre getTyre() {
    return tyre;
  }

  public void setTyre(Tyre tyre) {
    this.tyre = tyre;
  }

  public void drive() {
    System.out.println("car >" + tyre); // "car >Tyre..It's working.."
  }
}
```

```xml
<!-- spring.xml -->
<beans [custom tags definition]>
  <context:component-scan base-package="com.navin.Telusko"></context:component-scan>

  <!-- in this exmaple
  no xml based configuration is used -->
</beans>
```

```java
@Component //Annotation based configuration
public class Tyre {
  private String brand;

  public String getBrand() {
    return brand;
  }

  public void setBrand(String brand) {
    this.brand = brand;
  }

  @Override
  public String toString() {
    return "Tyre..It's working..";
  }
}
```


<br><br><br>
>xml-based configuration vs. java-based configuration  

:point_right:11. Configuration & Bean – 01:05:36

xml-based configuration  
```xml
<!-- spring.xml -->
<beans>
  <bean id="phone" class="mypackage.Samsung" />
  <bean id="cpu" class="mypackage.Snapdragon" />
</beans>
```
<br>
java-based configuration  
```java
// AppConfig.java
@Configuration
public class AppConfig {
  @Bean
  public Samsung getPhone() {
    return new Samsung(); //from Samsung class
  }

  @Bean
  public MobileProcessor getProcessor(){
    return new Snapdragon(); // from MobileProcessor class
  }
}
```
<br>
:point_right:12. Annotation Component AutoWired Primary Qualifier – 01:21:28

java-based configuration  
```java
// AppConfig.java
@Configuration
@ComponentScan(basePackages="[package-name-which-have-all-the-classes]")
public class AppConfig {
  //instead of @Bean tags..
  //add @Component code to every class you're going to use
}
```





peachpuff에 업로드  
telusko에게 블로그에 정리한 글 괜찮은지 물어보기
