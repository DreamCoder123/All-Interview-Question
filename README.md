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

10. Explain Bean life cycle in Spring Bean Factory Container.
The Bean life cycle is as follows:

The IoC container instantiates the bean from the bean’s definition in the XML file.
Spring then populates all of the properties using the dependency injection as specified in the bean definition.
The bean factory container calls setBeanName() which take the bean ID and the corresponding bean has to implement BeanNameAware interface.
The factory then calls setBeanFactory() by passing an instance of itself (if BeanFactoryAware interface is implemented in the bean).
If BeanPostProcessors is associated with a bean, then the preProcessBeforeInitialization() methods are invoked.
If an init-method is specified, then it will be called.
Lastly, postProcessAfterInitialization() methods will be called if there are any BeanPostProcessors associated with the bean that needs to be run post creation.

11. What do you understand by Bean Wiring.
When beans are combined together within the Spring container, they are said to be wired or the phenomenon is called bean wiring.
The Spring container should know what beans are needed and how the beans are dependent on each other while wiring beans. This is given by means of XML / Annotations / Java code-based configuration.

12. What is autowiring and name the different modes of it?
The IoC container autowires relationships between the application beans. Spring lets collaborators resolve which bean has to be wired automatically by inspecting the contents of the BeanFactory.
Different modes of this process are:

no: This means no autowiring and is the default setting. An explicit bean reference should be used for wiring.
byName: The bean dependency is injected according to the name of the bean. This matches and wires its properties with the beans defined by the same names as per the configuration.
byType: This injects the bean dependency based on type.
constructor: Here, it injects the bean dependency by calling the constructor of the class. It has a large number of parameters.
autodetect: First the container tries to wire using autowire by the constructor, if it isn't possible then it tries to autowire by byType.

13. What are the limitations of autowiring?
Overriding possibility: Dependencies are specified using <constructor-arg> and <property>  settings that override autowiring.
Data types restriction: Primitive data types, Strings, and Classes can’t be autowired.
   
Spring Boot Interview Questions
14. What do you understand by the term ‘Spring Boot’?
Spring Boot is an open-source, java-based framework that provides support for Rapid Application Development and gives a platform for developing stand-alone and production-ready spring applications with a need for very few configurations.
   
15. Explain the advantages of using Spring Boot for application development.
Spring Boot helps to create stand-alone applications which can be started using java.jar (Doesn’t require configuring WAR files).
Spring Boot also offers pinpointed ‘started’ POMs to Maven configuration.
Has provision to embed Undertow, Tomcat, Jetty, or other web servers directly.
Auto-Configuration: Provides a way to automatically configure an application based on the dependencies present on the classpath.
Spring Boot was developed with the intention of lessening the lines of code.
It offers production-ready support like monitoring and apps developed using spring boot are easier to launch.
   
16. Differentiate between Spring and Spring Boot.
The Spring Framework provides multiple features like dependency injection, data binding, aspect-oriented programming (AOP), data access, and many more that help easier development of web applications whereas Spring Boot helps in easier usage of the Spring Framework by simplifying or managing various loosely coupled blocks of Spring which are tedious and have a potential of becoming messy.
Spring boot simplifies commonly used spring dependencies and runs applications straight from a command line. It also doesn’t require an application container and it helps in monitoring several components and configures them externally.

17. What are the features of Spring Boot?
Spring Boot CLI – This allows you to Groovy / Maven for writing Spring boot application and avoids boilerplate code.
Starter Dependency – With the help of this feature, Spring Boot aggregates common dependencies together and eventually improves productivity and reduces the burden on
Spring Initializer – This is a web application that helps a developer in creating an internal project structure. The developer does not have to manually set up the structure of the project while making use of this feature.
Auto-Configuration – This helps in loading the default configurations according to the project you are working on. In this way, unnecessary WAR files can be avoided.
Spring Actuator – Spring boot uses actuator to provide “Management EndPoints” which helps the developer in going through the Application Internals, Metrics etc.
Logging and Security – This ensures that all the applications made using Spring Boot are properly secured without any hassle.


18. What does @SpringBootApplication annotation do internally?
As per the Spring Boot documentation, the @SpringBootApplication annotation is one point replacement for using @Configuration, @EnableAutoConfiguration and @ComponentScan annotations alongside their default attributes.
This enables the developer to use a single annotation instead of using multiple annotations thus lessening the lines of code. However, Spring provides loosely coupled features which is why we can use these annotations as per our project needs.

19. What are the effects of running Spring Boot Application as “Java Application”?
The application automatically launches the tomcat server as soon as it sees that we are running a web application.

20. What is Spring Boot dependency management system?
It is basically used to manage dependencies and configuration automatically without the need of specifying the version for any of that dependencies.
   
21. What are the possible sources of external configuration?
Spring Boot allows the developers to run the same application in different environments by making use of its feature of external configuration. This uses environment variables, properties files, command-line arguments, YAML files, and system properties to mention the required configuration properties for its corresponding environments. Following are the sources of external configuration:
Command-line properties – Spring Boot provides support for command-line arguments and converts these arguments to properties and then adds them to the set of environment properties.
Application Properties – By default, Spring Boot searches for the application properties file or its YAML file in the current directory of the application, classpath root, or config directory to load the properties.
Profile-specific properties – Properties are loaded from the application-{profile}.properties file or its YAML file. This file resides in the same location as that of the non-specific property files and the {profile} placeholder refers to an active profile or an environment.
   
22. Can we change the default port of the embedded Tomcat server in Spring boot?
Yes, we can change it by using the application properties file by adding a property of server.port and assigning it to any port you wish to.
For example, if you want the port to be 8081, then you have to mention server.port=8081. Once the port number is mentioned, the application properties file will be automatically loaded by Spring Boot and the specified configurations will be applied to the application.
   
23. Can you tell how to exclude any package without using the basePackages filter?
We can use the exclude attribute while using the annotation @SpringBootApplication as follows: 

@SpringBootApplication(exclude= {Student.class})
public class InterviewBitAppConfiguration {}
   
24. How to disable specific auto-configuration class?
You can use the exclude attribute of @EnableAutoConfiguration for this purpose as shown below:
@EnableAutoConfiguration(exclude = {InterviewBitAutoConfiguration.class})
If the class is not specified on the classpath, we can specify the fully qualified name as the value for the excludeName.

//By using "excludeName"
@EnableAutoConfiguration(excludeName={Foo.class})
You can add into the application.properties and multiple classes can be added by keeping it comma-separated.
   
25. Can the default web server in the Spring Boot application be disabled?
Yes! application.properties is used to configure the web application type, by mentioning spring.main.web-application-type=none.

26. What are the uses of @RequestMapping and @RestController annotations in Spring Boot?
@RequestMapping:
This provides the routing information and informs Spring that any HTTP request matching the URL must be mapped to the respective method.
org.springframework.web.bind.annotation.RequestMapping has to be imported to use this annotation.
@RestController:
This is applied to a class to mark it as a request handler thereby creating RESTful web services using Spring MVC. This annotation adds the @ResponseBody and @Controller annotation to the class.
org.springframework.web.bind.annotation.RestController has to be imported to use this annotation.
Check out more Interview Questions on Spring Boot here.

27. What is Spring AOP?
Spring AOP (Aspect Oriented Programming) is similar to OOPs (Object Oriented Programming) as it also provides modularity.
In AOP key unit is aspects or concerns which are nothing but stand-alone modules in the application. Some aspects have centralized code but other aspects may be scattered or tangled code like in the case of logging or transactions. These scattered aspects are called cross-cutting concern.
A cross-cutting concern such as transaction management, authentication, logging, security etc is a concern that could affect the whole application and should be centralized in one location in code as much as possible for security and modularity purposes.

28. What is an advice? Explain its types in spring.
An advice is the implementation of cross-cutting concerns can be applied to other modules of the spring application. Advices are of mainly 5 types:

Before:
This advice executes before a join point, but it does not have the ability to prevent execution flow from proceeding to the join point (unless it throws an exception).
To use this, use @Before annotation.
AfterReturning:
This advice is to be executed after a join point completes normally i.e if a method returns without throwing an exception.
To use this, use @AfterReturning annotation.
AfterThrowing:
This advice is to be executed if a method exits by throwing an exception.
To use this, use @AfterThrowing annotation.
After:
This advice is to be executed regardless of the means by which a join point exits (normal return or exception encounter).
To use this, use @After annotation.
Around:
This is the most powerful advice surrounds a join point such as a method invocation.
To use this, use @Around annotation.

29. What is Spring AOP Proxy pattern?
A proxy pattern is a well-used design pattern where a proxy is an object that looks like another object but adds special functionality to it behind the scenes.
Spring AOP follows proxy-based pattern and this is created by the AOP framework to implement the aspect contracts in runtime.
The standard JDK dynamic proxies are default AOP proxies that enables any interface(s) to be proxied. Spring AOP can also use CGLIB proxies that are required to proxy classes, rather than interfaces. In case a business object does not implement an interface, then CGLIB proxies are used by default.
   
All Remaining Questions Reference is here:- https://www.interviewbit.com/spring-interview-questions/#spring-framework-features
