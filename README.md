# All-Interview-Question

Q1. What is Spring Framework?
Spring is a powerful open-source, loosely coupled, lightweight, java framework meant for reducing the complexity of developing enterprise-level applications. This framework is also called the “framework of frameworks” as spring provides support to various other important frameworks like JSF, Hibernate, Structs, EJB, etc.

Q2. What are the features of Spring Framework?
Spring framework follows layered architecture pattern that helps in the necessary components selection along with providing a robust and cohesive framework for J2EE applications development.
The AOP (Aspect Oriented Programming) part of Spring supports unified development by ensuring separation of application’s business logic from other system services.
Spring provides highly configurable MVC web application framework which has the ability to switch to other frameworks easily.
Provides provision of creation and management of the configurations and defining the lifecycle of application objects.
Spring has a special design principle which is known as IoC (Inversion of Control) that supports objects to give their dependencies rather than looking for creating dependent objects.
Spring is a lightweight, java based, loosely coupled framework.
Spring provides generic abstraction layer for transaction management that is also very useful for container-less environments.
Spring provides a convenient API to translate technology-specific exceptions (thrown by JDBC, Hibernate or other frameworks) into consistent, unchecked exceptions. This introduces abstraction and greatly simplifies exception handling.

3. What is a Spring configuration file?
A Spring configuration file is basically an XML file that mainly contains the classes information and describes how those classes are configured and linked to each other. The XML configuration files are verbose and cleaner.

4. What do you mean by IoC (Inversion of Control) Container?
Spring container forms the core of the Spring Framework. The Spring container uses Dependency Injection (DI) for managing the application components by creating objects, wiring them together along with configuring and managing their overall life cycles. The instructions for the spring container to do the tasks can be provided either by XML configuration, Java annotations, or Java code.

5. What do you understand by Dependency Injection?
The main idea in Dependency Injection is that you don’t have to create your objects but you just have to describe how they should be created.

The components and services need not be connected by us in the code directly. We have to describe which services are needed by which components in the configuration file. The IoC container present in Spring will wire them up together.

In Java, the 2 major ways of achieving dependency injection are:
Constructor injection: Here, the IoC container invokes the class constructor with a number of arguments where each argument represents a dependency on the other class.
Setter injection: Here, the spring container calls the setter methods on the beans after invoking a no-argument static factory method or default constructor to instantiate the bean

6. Explain the difference between constructor and setter injection?
In constructor injection, partial injection is not allowed whereas it is allowed in setter injection.
The constructor injection doesn’t override the setter property whereas the same is not true for setter injection.
Constructor injection creates a new instance if any modification is done. The creation of a new instance is not possible in setter injection.
In case the bean has many properties, then constructor injection is preferred. If it has few properties, then setter injection is preferred

7. What are Spring Beans?
They are the objects forming the backbone of the user’s application and are managed by the Spring IoC container.
Spring beans are instantiated, configured, wired, and managed by IoC container.
Beans are created with the configuration metadata that the users supply to the container (by means of XML or java annotations configurations.)

8. How is the configuration meta data provided to the spring container?
There are 3 ways of providing the configuration metadata. They are as follows:

XML-Based configuration: The bean configurations and their dependencies are specified in XML configuration files. This starts with a bean tag as shown below:
   <bean id="interviewBitBean" class="org.intervuewBit.firstSpring.InterviewBitBean">
    <property name="name" value="InterviewBit"></property>
   </bean>
Annotation-Based configuration: Instead of the XML approach, the beans can be configured into the component class itself by using annotations on the relevant class, method, or field declaration.
Annotation wiring is not active in the Spring container by default. This has to be enabled in the Spring XML configuration file as shown below
<beans>
<context:annotation-config/>
<!-- bean definitions go here -->
</beans>
Java-based configuration: Spring Framework introduced key features as part of new Java configuration support. This makes use of the @Configuration annotated classes and @Bean annotated methods. Note that:
@Bean annotation has the same role as the <bean/> element.
Classes annotated with @Configuration allow to define inter-bean dependencies by simply calling other @Bean methods in the same class.

9. What are the bean scopes available in Spring?
The Spring Framework has five scope supports. They are:

Singleton: The scope of bean definition while using this would be a single instance per IoC container.
Prototype: Here, the scope for a single bean definition can be any number of object instances.
Request: The scope of the bean definition is an HTTP request.
Session: Here, the scope of the bean definition is HTTP-session.
Global-session: The scope of the bean definition here is a Global HTTP session.
Note: The last three scopes are available only if the users use web-aware ApplicationContext containers.


All Remaining Questions Reference is here:- https://www.interviewbit.com/spring-interview-questions/#spring-framework-features
