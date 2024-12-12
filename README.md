# AssignmentNotes

What is a Spring Bean?
1.	Definition:
o	A Spring Bean is an object that is instantiated, assembled, and managed by the Spring IoC (Inversion of Control) container.
o	These beans form the backbone of a Spring application, providing the business logic and interacting with the user or data layer.
2.	Lifecycle:
o	Creation: Beans are created when the application context is initialized.
o	Initialization: Custom initialization methods can be defined.
o	Usage: Beans are used throughout the application based on dependency injection.
o	Destruction: Beans can have custom destruction methods executed when the application context is closed.
3.	Bean Scopes:
o	Singleton: A single instance is created and shared across the application.
o	Prototype: A new instance is created every time the bean is requested.
o	Request/Session/Global Session: Scoped for web applications to manage lifecycle during HTTP requests or sessions.
4.	Configuration:
o	Beans can be defined in XML, Java-based configuration using @Bean, or automatically detected through @Component, @Service, @Repository, and @Controller.
________________________________________
What is Dependency Injection?
1.	Definition:
o	Dependency Injection (DI) is a design pattern that allows the inversion of control for object dependencies.
o	It enables objects to receive their dependencies from an external source (e.g., IoC container) rather than creating them internally.
2.	Types of Dependency Injection:
o	Constructor Injection: Dependencies are provided through the class constructor.
o	Setter Injection: Dependencies are injected through public setter methods.
o	Field Injection: Dependencies are injected directly into fields using annotations like @Autowired.
3.	Benefits:
o	Promotes loose coupling between objects.
o	Enhances testability by allowing mock dependencies to be injected.
o	Makes the codebase more maintainable and flexible.
4.	Spring Annotations:
o	@Autowired: Automatically wires the required dependency.
o	@Qualifier: Used to specify which bean to inject when multiple candidates exist.
________________________________________
What is the IoC Container?
1.	Definition:
o	The Inversion of Control (IoC) Container is the core of the Spring Framework responsible for managing the lifecycle and configuration of application objects (beans).
2.	Responsibilities:
o	Instantiating and managing beans.
o	Configuring dependencies between beans using Dependency Injection.
o	Handling bean scopes and their lifecycles.
3.	Types of IoC Containers:
o	BeanFactory: A basic IoC container providing fundamental functionalities.
o	ApplicationContext: An advanced IoC container that extends BeanFactory, offering additional features like internationalization, event propagation, and application lifecycle management.
4.	How it works:
o	The container reads configuration metadata (XML, annotations, or Java-based).
o	Based on this metadata, it initializes and wires the beans as needed.
________________________________________
What is the Application Context?
1.	Definition:
o	The ApplicationContext is a sub-interface of the IoC container in Spring, providing a more feature-rich container for managing beans and their dependencies.
2.	Key Features:
o	Internationalization (i18n): Supports messages and resource bundles for different locales.
o	Event Handling: Manages events within the application using event listeners.
o	Bean Post-Processing: Allows interception of bean initialization and destruction.
o	Integration with Spring AOP: Enables cross-cutting concerns like logging and security.
3.	Common Implementations:
o	ClassPathXmlApplicationContext: Loads context definitions from an XML file in the classpath.
o	AnnotationConfigApplicationContext: Configures the application context using Java-based annotations.
o	WebApplicationContext: Specialized for web applications.
________________________________________
What does @SpringBootApplication do?
1.	Definition:
o	@SpringBootApplication is a composite annotation in Spring Boot that simplifies the configuration and setup of a Spring Boot application.
2.	Components:
o	@Configuration: Marks the class as a source of bean definitions.
o	@EnableAutoConfiguration: Automatically configures beans based on the application's classpath and settings.
o	@ComponentScan: Scans for Spring components in the specified package and its sub-packages.
3.	Benefits:
o	Reduces boilerplate code for configuration.
o	Provides a convention-over-configuration approach, allowing rapid development.
o	Automatically configures key components like databases, web servers, and security.
________________________________________
What is the Dispatcher Servlet?
1.	Definition:
o	The Dispatcher Servlet is the central component of the Spring MVC framework, acting as a front controller that handles all incoming HTTP requests and responses.
2.	Responsibilities:
o	Request Mapping: Routes incoming requests to the appropriate controllers based on URL patterns.
o	Handler Execution: Invokes the appropriate controller methods to process the request.
o	View Resolution: Determines the view (e.g., JSP, Thymeleaf) to render the response.
o	Exception Handling: Delegates exception handling to configured handlers.
3.	How it Works:
o	The Dispatcher Servlet is declared in the web application's web.xml or automatically configured in Spring Boot.
o	It uses various strategies (e.g., HandlerMapping, ViewResolver) to process requests and produce responses.
________________________________________
What is a Logger?
1.	Definition:
o	A Logger is a component used in applications to log messages for debugging, monitoring, and auditing purposes.
2.	Logging Frameworks:
o	SLF4J (Simple Logging Facade for Java): A facade for different logging frameworks like Logback, Log4j, and java.util.logging.
o	Logback: A robust and widely-used logging framework.
o	Log4j: An older logging framework that is still popular in some applications.
3.	Importance:
o	Helps trace errors and application flow.
o	Provides insights into the application behavior in production.
o	Assists in identifying performance bottlenecks.
4.	Usage in Spring:
o	Spring Boot uses SLF4J with Logback as the default logging implementation.
o	Common logging levels: TRACE, DEBUG, INFO, WARN, ERROR.
o	Example usage:
java
Copy code
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class MyClass {
    private static final Logger logger = LoggerFactory.getLogger(MyClass.class);

    public void performTask() {
        logger.info("Task is being performed");
        logger.error("An error occurred");
    }
}

