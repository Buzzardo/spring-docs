== Spring Annotation Cheat Sheet

Spring includes a lot of annotations. Some are annotations created within Spring. Some are annotations called for by various Java specifications. The annotations fall into categories, as follows:

* <<Spring Framework>>
* <<REST>>
* <<HATEOAS>>
* <<Session>>
* <<Boot>>
* <<Integration>>
* <<Cloud>>
* <<Data>>
* <<Batch>>
* <<Aspect-oriented Programming>>
* <<Integration Testing>>
* <<JMX>>
* <<Task Execution and Scheduling>>
* <<Cache Abstraction>>
* <<Other>>

=== Spring Framework

The Spring Framework is the core project within Spring. The Spring Framework includes annotations in the following categories:

* <<Dependency Injection>>
* <<Configuration>>
* <<JMS>>
* <<AMQP>>
* <<Bean Lifecycle>>
* <<MVC/Web>>
* <<CORS Support>>

==== Dependency Injection

Spring's dependency injection capability includes the following annotations:

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-resource-annotation[@Resource]:: Injects the requested resource.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-autowired-annotation[@Autowired]:: Widely used dependency injection mechanism for constructors, methods, and interfaces.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-inject-named[@Inject]:: A dependency injection mechanism that can replace @Autowired. @Named may also be used in place of @Autowired and @Inject.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-inject-named[@Named]:: A dependency injection mechanism that can replace @Autowired and @Inject. @Named may also be used in place of @Autowired and @Inject. @Named is also equivalent to @Component and @ManagedBean.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-named[@ManagedBean]:: A dependency injection mechanism that can replace @Autowired and @Inject. @ManagedBean is also equivalent to @Component and @Named. However, it is not composable.
https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/beans/factory/annotation/Value.html[@Value]:: Injection mechanism for fields and methods that indicates a default value. Often used to get values from property files.
https://docs.spring.io/spring/docs/current/javadoc-api/index.html?org/springframework/beans/factory/annotation/Required.html[@Required]:: Marks a method (typically a JavaBean setter method) as being 'required'. That is, the method must be configured to be dependency-injected with a value.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-autowired-annotation-primary[@Primary]:: Indicates that a particular bean should be given preference when multiple beans are candidates to be autowired to a single-valued dependency. If exactly one 'primary' bean exists among the candidates, it will be the autowired value.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-stereotype-annotations[@Component]:: Generic stereotype for any Spring-managed component.
https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/stereotype/Service.html[@Service]:: Indicates that an annotated class is a service.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-java-using-import[@Import]:: Allows for loading `@Bean` definitions from another configuration class.
https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/context/annotation/DependsOn.html[@DependsOn]:: Indicates beans on which the current bean depends.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-factory-collaborators[@ConstructorProperties]:: Used to explicitly name your constructor arguments.
http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/beans/factory/annotation/Lookup.html[@Lookup]:: Indicates 'lookup' methods, to be overridden by the container to redirect them back to the BeanFactory for a getBean call. This is essentially an annotation-based version of the XML lookup-method attribute.
http://docs.spring.io/spring/docs/4.3.0.RC1/javadoc-api//org/springframework/core/annotation/AliasFor.html[@AliasFor]:: Used to declare aliases for annotation attributes.

==== Configuration

Spring's configuration capability includes the following annotations:

[horizontal]
https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/context/annotation/ComponentScan.html[@ComponentScan]:: Configures component scanning directives for use with @Configuration classes.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-java-basic-concepts[@Configuration]:: Indicates that the primary purpose of the annotated class is to provide a source of bean definitions.
https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/core/annotation/Order.html[@Order]:: Defines the sort order for an annotated component. Lower values have higher priority. @Priority can replace @Order.
http://docs.oracle.com/javaee/7/api/javax/annotation/Priority.html[@Priority]:: Defines the sort order for an annotated component. Lower values have higher priority. @Order can replace @Priority.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-autowired-annotation-qualifiers[@Qualifier]:: Associates a value with a particular argument. More finely tuned way than @Order and @Priority to control selection.
https://docs.oracle.com/javase/8/docs/api/java/lang/annotation/Target.html[@Target]:: Indicates the contexts in which an annotation type is applicable.
https://docs.oracle.com/javase/8/docs/api/java/lang/annotation/Retention.html[@Retention]:: Indicates how long annotations with the annotated type are to be retained.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-autowired-annotation-qualifiers[@interface]:: Lets you create custom annotations to use as qualifiers.
https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/stereotype/Repository.html[@Repository]:: Indicates that an annotated class is a repository.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-definition-profiles[@Profile]:: Indicates that a component is eligible for registration when one or more specified profiles are active.
https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/context/annotation/Conditional.html[@Conditional]:: Indicates that a component is only eligible for registration when all specified conditions match.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-java-using-import[@ImportResource]:: Allows for loading @Bean definitions from another configuration class. Also allows for importing XML configuration files.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#context-load-time-weaver[@EnableLoadTimeWeaving]:: Enables load-time weaving, which is used by Spring to dynamically transform classes as they are loaded into the JVM.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#context-functionality-events-annotation[@EventListener]:: Registers an event listener on a public method of a bean.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#context-functionality-events-async[@Async]:: Specifies that an event listener is asynchronous. See also: Async under <<Task Execution and Scheduling>>.
https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/context/annotation/PropertySource.html[@PropertySource]:: Adds a PropertySource to Spring's Environment.

==== JMS

Spring's support for JMS includes the following annotations:

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/jms.html#jms-annotated-support[@EnableJms]:: Add to an @configuration class to enable support for @JmsListener annotations.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/jms.html#jms-mdp[@JmsListener]:: Indicates that a method of a managed bean is a JMS listener endpoint.
http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/jms/annotation/JmsListeners.html[@JmsListeners]:: Aggregates several @JmsListener annotations. On Java 8, it can be replaced by repeatable @JmsListener annotations.
http://docs.spring.io/spring-integration/reference/html/message-publishing.html[@Payload]:: Indicates that a method provides the payload of a message.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/jms.html#jms-annotated-response[@SendTo]:: Indicates the method (or sometimes class) that responds to a message.
http://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/messaging/simp/annotation/SendToUser.html[@SendToUser]:: Indicates that the return value of a message-handling method should be sent as a Message to the specified destination(s) prepended with `/user/{username}` where the user name is extracted from the headers of the input message being handled.

==== AMQP

Spring AMQP provides the following annotations:

[horizontal]
http://docs.spring.io/spring-amqp/docs/current/api/org/springframework/amqp/rabbit/annotation/Queue.html[@Queue]:: A queue definition used within the bindings attribute of an `@QueueBinding`.
http://docs.spring.io/spring-amqp/docs/current/api/org/springframework/amqp/rabbit/annotation/QueueBinding.html[@QueueBinding]:: Defines a queue, the exchange it is to be bound to, and an optional binding key. Used with `@RabbitListener`.
http://docs.spring.io/spring-amqp/docs/current/api/org/springframework/amqp/rabbit/annotation/Exchange.html[@Exchange]:: Defines an exchange to which to bind a RabbitListener queue.
http://docs.spring.io/spring-amqp/docs/current/api/org/springframework/amqp/rabbit/annotation/Argument.html[@Argument]:: Represents an argument used when declaring queues etc within a QueueBinding.
http://docs.spring.io/spring-amqp/docs/current/api/org/springframework/amqp/rabbit/annotation/EnableRabbit.html[@EnableRabbit]:: Enable Rabbit listener annotated endpoints that are created behind the scenes by a `RabbitListenerContainerFactory`. To be used on `@Configuration` classes.
http://docs.spring.io/spring-amqp/docs/current/api/org/springframework/amqp/rabbit/annotation/RabbitHandler.html[@RabbitHandler]:: marks a method to be the target of a Rabbit message listener within a class that is annotated with `@RabbitListener`.
http://docs.spring.io/spring-amqp/api/org/springframework/amqp/rabbit/annotation/RabbitListener.html[@RabbitListener]:: Marks a method as the target of a Rabbit message listener on the specified `queues` (or `bindings`).
http://docs.spring.io/spring-amqp/docs/current/api/org/springframework/amqp/rabbit/annotation/RabbitListeners.html[@RabbitListeners]:: Container annotation that aggregates several `@RabbitListener` annotations.
http://docs.spring.io/spring-amqp/docs/current/api/org/springframework/amqp/rabbit/test/RabbitListenerTest.html[@RabbitListenerTest]:: Enables proxying of @RabbitListener beans to capture arguments and results (if any). Used on @Configuration classes.

==== Bean Lifecycle

Spring's bean lifecycle management capability includes the following annotations:

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/expressions.html#expressions-bean-references[@{BeanName}]:: For example, `@foo` will find a bean named `foo`, provided the evaluation context has been configured with a bean resolver.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-java-basic-concepts[@Bean]:: Indicates that a method instantiates, configures and initializes a new object to be managed by the Spring IoC container.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-java-bean-description[@Description]:: Adds a description to a bean.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-stereotype-annotations[@Component]:: Generic stereotype for any Spring-managed component.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-factorybeans-annotations[@Lazy]:: Causes lazy resolution of a bean in the IoC container.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-scanning-scope-resolver[@Scope]:: Specifies a non-default scope for a component.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-postconstruct-and-predestroy-annotations[@PostConstruct]:: Identifies a method to be called after an instance of a bean has been constructed. Used to populate caches and similar operations.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/beans.html#beans-postconstruct-and-predestroy-annotations[@PreDestroy]:: Identifies a method to be called before an instance of a bean is to be destroyed. Used to de-populate caches and similar operations.

==== MVC/Web

Spring provides the following annotations for web applications:
Major source: https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-config-enable[@EnableWebMvc]:: Added to a @configuration class to enable Web MVC.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-controller[@Controller]:: Indicates that a class is an MVC controller.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-restcontroller[@RESTController]:: Indicates that a class is a REST controller.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-controller[@RequestMapping]:: Associates a URI path with a method in a controller.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-modelattrib-methods[@ModelAttribute]:: Indicates that a method or argument contributes to a model.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-sessionattrib-global[@SessionAttribute]:: Provides access to pre-existing session attributes that are managed globally.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-sessionattrib[@SessionAttributes]:: Declares session attributes used by a specific handler.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-responsebody[@ResponseBody]:: Causes the return type to be written to the response body (rather than the model).
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-requestparam[@RequestParam]:: Binds a request parameter to a method.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-multipart-forms-non-browsers[@RequestPart]:: Associates a handler method argument with part of a multi-part request.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-requestmapping-uri-templates[@PathVariable]:: Binds a method argument to the value of a URI template variable.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Header.html[@Header]:: Indicates that a method parameter's value should be retrieved from the message headers.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Headers.html[@Headers]:: Deprecated. Use @header.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-requestheader[@RequestHeader]:: Binds a method parameter to a request header.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-requestbody[@RequestBody]:: Binds a method parameter to the value of the HTTP request body.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-annotated-exceptions[@ResponseStatus]:: Indicates a business exception.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-controller-advice[@ControllerAdvice]:: Allows implementation classes to be auto-detected through classpath scanning. It is automatically enabled when using the MVC namespace or the MVC Java config.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-controller-advice[@RestControllerAdvice]:: As @ControllerAdvice (previous) but `@ExceptionHandler` methods assume `@ResponseBody` semantics by default.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/portlet.html#portlet-ann-initbinder[@InitBinder]:: Configures web data binding directly within a controller class.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-matrix-variables[@MatrixVariable]:: Identifies the value part of a name/value pair in a URI path.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-cookievalue[@cookieValue]:: Binds a method parameter to the value of an HTTP cookie.
http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/context/annotation/RequestScope.html[@RequestScope]:: A specialization of @Scope for a component whose lifecycle is bound to the current web request.
http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/context/annotation/SessionScope.html[@SessionScope]:: A specialization of @Scope for a component whose lifecycle is bound to the current web session.
http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/context/annotation/ApplicationScope.html[@ApplicationScope]:: A specialization of @Scope for a component whose lifecycle is bound to the current web application.

Spring MVC provides the following convenience annotations for request mapping:

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-requestmapping-composed[@GetMapping]:: Shortcut for @RequestMapping(method = RequestMethod.GET)
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-requestmapping-composed[@PostMapping]:: Shortcut for @RequestMapping(method = RequestMethod.POST)
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-requestmapping-composed[@PutMapping]:: Shortcut for @RequestMapping(method = RequestMethod.PUT)
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-requestmapping-composed[@DeleteMapping]:: Shortcut for @RequestMapping(method = RequestMethod.DELETE)
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-requestmapping-composed[@PatchMapping]:: Shortcut for @RequestMapping(method = RequestMethod.PATCH)

==== CORS Support

Spring MVC/Web includes a single annotation for managing Cross-Origin Resource Support (CORS):

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cors.html#_controller_method_cors_configuration[@CrossOrigin]:: Enables cross-origin resource sharing (CORS) on a path.

=== Security

Spring Security provides the following annotations:

[horizontal]
https://docs.spring.io/spring-security/site/docs/current/apidocs/org/springframework/security/config/annotation/web/configuration/EnableWebSecurity.html[@EnableWebSecurity]:: Adds Spring Security configuration defined in a WebSecurityConfigurer (often by extending WebSecurityConfigurerAdapter). Must be added to an @Configuration class.
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#enableglobalmethodsecurity[@EnableGlobalMethodSecurity]:: Class-level annotation that turns on method-level security. Must be on an @Configuration class. You must add other annotations to each method to be secured.
https://docs.spring.io/spring-security/site/docs/4.2.3.RELEASE/apidocs/[@Secured]:: Defines a list of security configuration attributes for business methods.
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#el-pre-post-annotations[@PreAuthorize]:: Determines whether a method can actually be invoked or not, usually based on a user role.
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#el-pre-post-annotations[@PostAuthorize]:: Performs an access-control check after the method has been invoked.
http://docs.spring.io/spring-security/site/docs/current/apidocs/org/springframework/security/test/context/annotation/SecurityTestExecutionListeners.html[@SecurityTestExecutionListeners]:: Enables only the Spring Security `TestExecutionListener` classes (rather than all Spring `TestExecutionListener` classes)
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#test-method-withmockuser[@WithMockUser]:: Runs a test as a specified mock user.
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#test-method-withanonymoususer[@WithAnonymousUser]:: Runs a test as an anonymous user.
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#test-method-withuserdetails[@WithUserDetails]:: Runs a test with user details provided by a custom `UserDetailsService`.
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#test-method-withsecuritycontext[@WithSecurityContext]:: Runs a test with a custom `SecurityContext`.
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#filtering-using-prefilter-and-postfilter[@PostFilter]:: After a method has been called, iterates through a returned collection and removes any item that doesn't match the filter.
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#filtering-using-prefilter-and-postfilter[@PreFilter]:: Before a method is called, iterates through a collection and removes any item that doesn't match the filter. (Used much more rarely than @PostFilter).
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#mvc-enablewebmvcsecurity[@EnableWebMvcSecurity]:: Enables Spring Security integration with Spring MVC.
http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#mvc-authentication-principal[@AuthenticationPrincipal]:: Automatically resolves the current `Authentication.getPrincipal()` for Spring MVC arguments.
http://docs.spring.io/spring-security/oauth/apidocs/org/springframework/security/oauth2/config/annotation/web/configuration/EnableAuthorizationServer.html[@EnableAuthorizationServer]:: Convenience annotation for enabling an authorization Server (that is, an `AuthorizationEndpoint` and a `TokenEndpoint`) in the current application context, which must be a `DispatcherServlet` context.
http://docs.spring.io/spring-security/oauth/apidocs/org/springframework/security/oauth2/config/annotation/web/configuration/EnableResourceServer.html[@EnableResourceServer]:: Convenience annotation for OAuth2 Resource Servers, enabling a Spring Security filter that authenticates requests via an incoming OAuth2 token.
http://docs.spring.io/spring-security/oauth/apidocs/org/springframework/security/oauth2/config/annotation/web/configuration/EnableOAuth2Client.html[@EhableOAuth2Client]:: Enables configuration for an OAuth2 client in a web application that wants to use the Authorization Code Grant from one or more OAuth2 Authorization servers.
https://docs.spring.io/spring-integration/api/org/springframework/integration/security/channel/SecuredChannel.html[@SecuredChannel]:: Applies the `ChannelSecurityInterceptor`(s) using provided `interceptor()` bean name(s).

==== Spring WebSocket

Spring MVC/Web includes the following annotations for working with WebSockets:

[horizontal]
http://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/socket/config/annotation/EnableWebSocket.html[@EnableWebSocket]:: Enables the processing of WebSocket requests. Must be added to an `@Configuration` class.
http://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/socket/config/annotation/EnableWebSocketMessageBroker.html[@EnableWebSocketMessageBroker]:: Enables broker-backed messaging over WebSocket using a higher-level messaging sub-protocol. Must be added to an `@Configuration` class.
http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/messaging/handler/annotation/MessageMapping.html[@MessageMapping]:: Maps a Message onto message-handling methods by matching to the message destination.
http://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/messaging/handler/annotation/DestinationVariable.html[@DestinationVariable]:: Indicates that a method parameter should be bound to a template variable in a destination template string.
http://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/messaging/simp/annotation/SubscribeMapping.html[@SubscribeMapping]:: Maps subscription messages onto specific handler methods based on the destination of a subscription.

=== REST

Spring Data REST provides the following annotations:

[horizontal]
http://docs.spring.io/autorepo/docs/spring-data-rest/2.1.x/api/org/springframework/data/rest/core/annotation/RepositoryRestResource.html[@RepositoryRestResource]:: Marks a repository for custom export mapping and rel attributes.
http://docs.spring.io/autorepo/docs/spring-data-rest/2.1.x/api/org/springframework/data/rest/core/annotation/Description.html[@Description]:: Describes the semantics of a resource.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/HandleAfterCreate.html[@HandleAfterCreate]:: Indicates a component that should handle the `afterCreate` event.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/HandleAfterDelete.html[@HandleAfterDelete]:: Indicates a component that should handle the `afterDelete` event.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/HandleAfterLinkSave.html[@HandleAfterLinkSave]:: Indicates a component that should handle the `afterLinkSave` event.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/HandleAfterSave.html[@HandleAfterSave]:: Indicates a component that should handle the `afterSave` event.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/HandleBeforeCreate.html[@HandleBeforeCreate]:: Indicates a component that should handle the `beforeCreate` event.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/HandleBeforeDelete.html[@HandleBeforeDelete]:: Indicates a component that should handle the `beforeDelete` event.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/HandleBeforeLinkDelete.html[@HandleBeforeLinkDelete]:: Indicates a component that should handle the `beforeLinkDelete` event.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/HandleBeforeLinkSave.html[@HandleBeforeLinkSave]:: Indicates a component that should handle the `beforeLinkSave` event.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/HandleBeforeSave.html[@HandleBeforeSave]:: Indicates a component that should handle the `beforeSave` event.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/RepositoryEventHandler.html[@RepositoryEvenHandler]:: Class-level annotation that indicates that the class is an event handler for a repository.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/annotation/RestResource.html[@RestResource]:: Indicates how a repository should be exported and what the value of the rel attribute in links will be.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/core/config/Projection.html[@Projection]:: Ties a particular projection type to a source type. Used to find projection interfaces at startup time.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/Version.html[@Version]:: Identifies a property to be used as version field to implement optimistic locking on entities.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/AccessType.html[@AccessType]:: Defines how Spring Data accesses values of persistent properties.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/CreatedBy.html[@CreatedBy]:: Declares a field as the one representing the principal that created the entity containing the field.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/CreatedDate.html[@CreatedDate]:: Declares a field as the one representing the date the entity containing the field was created.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/Id.html[@Id]:: Indicates an identifier.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/LastModifiedBy.html[@LastModifiedBy]:: Declares a field as the one representing the principal that recently modified the entity containing the field.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/LastModifiedDate.html[@LastModifiedDate]:: Declares a field as the one representing the date the entity containing the field was recently modified.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/PersistenceConstructor.html[@PersistenceConstructor]:: Indicates that a constructor, even one that’s package protected, as the primary constructor used by the persistence logic.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/Persistent.html[@Persistent]:: Indicates that a field should be persisted even if there are no getter and setter methods for it.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/QueryAnnotation.html[@QueryAnnotation]:: Meta-Annotation to mark a store-specific annotation as a query annotation. This allows generic special handing of finder methods on Repository interfaces.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/ReadOnlyProperty.html[@ReadOnlyProperty]:: Marks a field as read-only for the mapping framework. The field will not be persisted.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/Reference.html[@Reference]:: Meta-annotation to indicate annotations that mark references to other objects.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/Transient.html[@Transient]:: Marks a field to be transient for the mapping framework.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/annotation/TypeAlias.html[@TypeAlias]:: Lets `String` based type aliases to be used when writing type information for `PersistentEntity` objects.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/webmvc/BasePathAwareController.html[@BasePathAwareController]:: Indicates a controller that declares request mappings to be augmented with a base URI in the Spring Data REST configuration.
http://docs.spring.io/spring-data/rest/docs/current/api/org/springframework/data/rest/webmvc/RepositoryRestController.html[@RepositoryRestController]:: Identifies Spring MVC controllers provided by Spring Data REST.

=== HATEOAS

Spring HATEOAS provides the following annotations:

http://docs.spring.io/spring-hateoas/docs/0.23.0.RELEASE/reference/html/#configuration.at-enable[@EnableHypermediaSupport]:: Enables support for a particular hypermedia representation type.
http://docs.spring.io/spring-hateoas/docs/0.23.0.RELEASE/reference/html/#fundamentals.obtaining-links.entity-links[@EnableEntityLinks]:: Enables dependency injection of `EntityLinks` objects.
http://docs.spring.io/spring-hateoas/docs/0.23.0.RELEASE/reference/html/#fundamentals.obtaining-links.entity-links[@ExposesResourceFor]:: Class-level annotation for controllers. Indicates which model type the controller manages.
http://docs.spring.io/spring-hateoas/docs/0.23.0.RELEASE/reference/html/#configuration.at-enable[@Relation]:: Indicates the relation to be used when embedding objects in hypermedia.

=== Session

Spring Session provides the following annotations:

https://docs.spring.io/spring-session/docs/current-SNAPSHOT/api/org/springframework/session/data/redis/config/annotation/web/http/EnableRedisHttpSession.html[@EnableRedisHttpSession]:: Exposes the SessionRepositoryFilter as a bean named "springSessionRepositoryFilter" and backed by Redis. Must be added to an @Configuration class.
http://docs.spring.io/spring-session/docs/current/api/org/springframework/session/data/gemfire/config/annotation/web/http/EnableGemFireHttpSession.html[@EnableGemFireHttpSession]:: Exposes the SessionRepositoryFilter as a bean named "springSessionRepositoryFilter" and backed by Pivotal GemFire or Apache Geode. Must be added to an @Configuration class.
http://docs.spring.io/spring-session/docs/current/api/org/springframework/session/jdbc/config/annotation/web/http/EnableJdbcHttpSession.html[@EnableJdbcHttpSession]:: Exposes the SessionRepositoryFilter as a bean named "springSessionRepositoryFilter" and backed by a relational database. Must be added to an @Configuration class.
http://docs.spring.io/spring-session/docs/current/api/org/springframework/session/data/mongo/config/annotation/web/http/EnableMongoHttpSession.html[@EnableMongoHttpSession]:: Exposes the SessionRepositoryFilter as a bean named "springSessionRepositoryFilter" and backed by Mongo. Must be added to an @Configuration class.
http://docs.spring.io/spring-session/docs/current/api/org/springframework/session/hazelcast/config/annotation/web/http/EnableHazelcastHttpSession.html[@EnableHazelcastHttpSession]:: Exposes the SessionRepositoryFilter as a bean named "springSessionRepositoryFilter" and backed by Hazelcast. Must be added to an @Configuration class.
http://docs.spring.io/spring-session/docs/current/api/org/springframework/session/config/annotation/web/http/EnableSpringHttpSession.html[@EnableSpringHttpSession]:: Exposes the SessionRepositoryFilter as a bean named "springSessionRepositoryFilter" and backed by a user provided implementation of SessionRepository. Must be added to an @Configuration class.

=== Boot

Spring Boot provides the following annotations:

http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#using-boot-using-springbootapplication-annotation[@SpringBootApplication]:: Convenience annotation that includes @Configuration, @EnableAutoConfiguration, and @ComponentScan
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#getting-started-first-application-auto-configuration[@EnableAutoConfiguration]:: tells Spring Boot to determine how you will want to configure Spring, based on the jar dependencies that you have added.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/domain/EntityScan.html[@EntityScan]:: Configures the base packages used by auto-configuration when scanning for entity classes.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-external-config[@ConfigurationProperties]:: Identifies a class a configuration properties class, which can then be used to control and validate configuration.
http://docs.spring.io/autorepo/docs/spring-boot/1.2.0.M2/api/org/springframework/boot/context/properties/EnableConfigurationProperties.html[@@EnableConfigurationProperties]:: Enables support for `@ConfigurationProperties` annotated beans.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/context/properties/ConfigurationPropertiesBinding.html[@ConfigurationPropertiesBinding]:: Qualifier for beans that are needed to configure the binding of `ConfigurationProperties` (often converters).
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-json-components[@JsonComponent]:: Provides JsonSerializer and/or JsonDeserializer implementations to be registered with Jackson when `JsonComponentModule` is in use.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-embedded-container-context-initializer[@ServletComponentScan]:: Enables automatic registration of classes annotated with @WebServlet, @WebFilter, and @WebListener.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/security/oauth2/client/EnableOAuth2Sso.html[@EnableOAuth2Sso]:: Enables OAuth2 Single Sign On (SSO).
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-testing-spring-boot-applications[@SpringBootTest]:: Creates an `ApplicationContext` object that supports testing a Spring Boot application.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-testing-spring-boot-applications[@AutoConfigureMockMvc]:: Configures a `MockMvc` object for use when testing Spring Boot applications.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/SpringBootConfiguration.html[@SpringBootConfiguration]:: Indicates that a class provides Spring Boot application `@Configuration`. Can be used as an alternative to the Spring's standard `@Configuration` annotation so that configuration can be found automatically (for example in tests). An application should include only one @SpringBootConfiguration, and most idiomatic Spring Boot applications will inherit it from @SpringBootApplication.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/context/TestConfiguration.html[@TestConfiguration]:: @Configuration that can be used to define additional beans or customizations for a test. Unlike regular @Configuration classes the use of @TestConfiguration does not prevent auto-detection of @SpringBootConfiguration.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/context/embedded/LocalServerPort.html[@LocalServerPort]:: Annotation at the field or method/constructor parameter level that injects the HTTP port that got allocated at runtime. Provides a convenient alternative for `@Value("${local.server.port}")`.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/mock/mockito/MockBean.html[@MockBean]:: Adds a mock bean to a Spring `ApplicationContext`.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/mock/mockito/SpyBean.html[@Spybean]:: Applies Mockito spies to a Spring `ApplicationContext`.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/ImportAutoConfiguration.html[@ImportAutoConfiguration]:: Imports and applies the specified auto-configuration classes. Sometimes useful for testing. Generally, @EnableAutoConfiguration should be preferred.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-testing-spring-boot-applications-testing-autoconfigured-json-tests[@JsonTest]:: Auto-configures Jackson `ObjectMapper`, any `@JsonComponent` beans and any Jackson `Modules`.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/autoconfigure/web/servlet/WebMvcTest.html[@WebMvcTest]:: Used with @RunWith(SpringRunner.class) for a typical Spring MVC test. Can be used when a test focuses only on Spring MVC components. Using this annotation will disable full auto-configuration and instead apply only configuration relevant to MVC tests.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/autoconfigure/orm/jpa/DataJpaTest.html[@DataJpaTest]:: Annotation that can be used in combination with `@RunWith(SpringRunner.class)` for a typical JPA test. Can be used when a test focuses *only* on JPA components.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/autoconfigure/orm/jpa/AutoConfigureTestEntityManager.html[@AutoConfigureTestEntityManager]:: Can be applied to a test class to enable auto-configuration of a TestEntityManager.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/test/autoconfigure/orm/jpa/AutoConfigureTestDatabase.html[@AutoConfigureTestDatabase]:: Can be applied to a test class to configure a test database to use instead of any application defined or auto-configured DataSource.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-testing-spring-boot-applications-testing-autoconfigured-jdbc-test[@JdbcTest]:: Annotation that can be used in combination with `@RunWith(SpringRunner.class)` for a typical JDBC test. By default, it will also configure an in-memory embedded database and a `JdbcTemplate`.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-testing-spring-boot-applications-testing-autoconfigured-mongo-test[@DataMongoTest]:: Used to test MongoDB applications. By default, it will configure an in-memory embedded MongoDB (if available), configure a MongoTemplate, scan for @Document classes and configure Spring Data MongoDB repositories.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-testing-spring-boot-applications-testing-autoconfigured-rest-client[@RestClientTest]:: Used to test REST clients. By default, it will auto-configure Jackson and GSON support, configure a RestTemplateBuilder and add support for MockRestServiceServer.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-testing-spring-boot-applications-testing-autoconfigured-rest-docs[@AutoConfigureRestDocs]:: Used to use Spring REST Docs in your tests. It will automatically configure MockMvc to use Spring REST Docs and remove the need for Spring REST Docs' JUnit rule.
http://docs.spring.io/autorepo/docs/spring-boot/1.2.6.RELEASE/api/org/springframework/boot/test/WebIntegrationTest.html[@WebIntegrationTest]:: Test class annotation signifying that the tests are "web integration tests" and therefore require full startup in the same way as a production application (listening on normal ports). Normally used in conjunction with `@SpringApplicationConfiguration`.
http://docs.spring.io/autorepo/docs/spring-boot/1.2.6.RELEASE/api/org/springframework/boot/test/SpringApplicationConfiguration.html[@SpringApplicationConfiguration]:: Class-level annotation that is used to determine how to load and configure an ApplicationContext for integration tests. Similar to the standard `ContextConfiguration` but uses Spring Boot's `SpringApplicationContextLoader`.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/condition/ConditionalOnClass.html[@ConditionalOnClass]:: Matches only when the specified classes are on the classpath.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/condition/ConditionalOnMissingBean.html[@ConditionalOnMissingBean]:: Matches only when the specified bean classes and/or names are not already contained in the BeanFactory.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-locating-auto-configuration-candidates[@AutoConfigureBefore]:: Used when configurations need to be loaded in a particular order.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-locating-auto-configuration-candidates[@AutoConfigureAfter]:: Used when configurations need to be loaded in a particular order.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#boot-features-locating-auto-configuration-candidates[@AutoconfigureOrder]:: Allows for ordering certain auto-configurations that shouldn’t have any direct knowledge of each other.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/condition/ConditionalOnProperty.html[@ConditionalOnProperty]:: Checks whether the specified properties have the specified value.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/condition/ConditionalOnResource.html[@ConditionalOnResource]:: Lets configuration to be included only when a specific resource is present.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/condition/ConditionalOnWebApplication.html[@ConditionalOnWebApplication]:: Matches only when the application context is a web application
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/condition/ConditionalOnNotWebApplication.html[@ConditionalOnNotWebApplication]:: Matches only when the application context is not a web application.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/condition/ConditionalOnExpression.html[@ConditionalOnExpression]:: Lets configuration be included based on the result of a SpEL expression.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/autoconfigure/ManagementContextConfiguration.html[@ManagementContextConfiguration]:: Specialized @Configuration class that defines configuration specific for the management context. Configurations should be registered in /META-INF/spring.factories under the org.springframework.boot.actuate.autoconfigure.ManagementContextConfiguration key.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/autoconfigure/ExportMetricWriter.html[@ExportMetricWriter]:: Qualifier annotation for a metric repository that is to be used to export metrics from the ExportMetricReader readers.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/actuate/autoconfigure/ExportMetricReader.html[@ExportMetricReader]:: Qualifier annotation for a metric reader that can be exported (to distinguish it from others that might be installed by the user for other purposes).
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#howto-execute-flyway-database-migrations-on-startup[@FlywayDataSource]:: Specifies a DataSource to be injected into Flyway. If used for a second data source, the other (main) one would normally be marked as `{@code @Primary}`.
http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#howto-execute-liquibase-database-migrations-on-startup[@LiquibaseDataSource]:: Specifies a DataSource to be injected into Liquibase. If used for a second data source, the other (main) one would normally be marked as `{@code @Primary}`.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/context/properties/DeprecatedConfigurationProperty.html[@DeprecatedConfigurationProperty]:: Indicates that a getter in a `ConfigurationProperties` object is deprecated. This annotation has no bearing on the actual binding processes, but it is used by the `spring-boot-configuration-processor` to add deprecation meta-data.
http://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/context/properties/NestedConfigurationProperty.html[@NestedConfigurationProperty]:: Indicates that a field in a ConfigurationProperties object should be treated as if it were a nested type.

=== Integration

Spring integration includes the following annotations:

https://docs.spring.io/spring-integration/api/org/springframework/integration/config/EnableIntegration.html[@EnableIntegration]:: Enables Spring Integration infrastructure, registers built-in beans, adds BeanFactoryPostProcessors, adds BeanPostProcessors, and adds annotation processors.
http://docs.spring.io/spring-integration/api/org/springframework/integration/config/EnableIntegrationManagement.html[@EnableIntegrationManagement]:: Enables default configuration of management in Spring Integration components in an existing application.
http://docs.spring.io/spring-integration/api/org/springframework/integration/config/EnableMessageHistory.html[@EnableMessageHistory]:: Enables MessageHistory for Integration components.
http://docs.spring.io/spring-integration/api/org/springframework/integration/config/EnablePublisher.html[@EnablePublisher]:: Provides the registration for the PublisherAnnotationBeanPostProcessor to allow the use of the Publisher annotation.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/IntegrationComponentScan.html[@IntegrationComponentScan]:: Configures component scanning directives for use with Configuration classes.
https://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Publisher.html[@Publisher]:: Indicates that a method (or all public methods if applied at class-level) should publish Messages.
https://docs.spring.io/spring-integration/api/org/springframework/integration/config/GlobalChannelInterceptor.html[@GlobalChannelInterceptor]:: `ChannelInterceptor` components with this annotation will be applied as global channel interceptors using the provided patterns to match channel names.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Aggregator.html[@Aggregator]:: Indicates that a method is capable of aggregating messages.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/BridgeFrom.html[@BridgeFrom]:: Marks a `Bean` method for a `MessageChannel` to produce a `BridgeHandler` and `Consumer Endpoint`.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/BridgeTo.html[@BridgeTo]:: Marks a Bean method for a MessageChannel to produce a BridgeHandler and Consumer Endpoint.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/CorrelationStrategy.html[@CorrelationStrategy]:: Indicates that a given method is capable of determining the correlation key of a message sent as parameter.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Filter.html[@Filter]:: Indicates that a method is capable of playing the role of a Message Filter.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Gateway.html[@Gateway]:: Indicates that an interface method is capable of mapping its parameters to a message or message payload.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/GatewayHeader.html[@GatewayHeaer]:: Provides the message header value or expression.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/IdempotentReceiver.html[@IdempotentReceiver]:: A method that has a Messaging annotation (`@code`, `@ServiceActivator`, `@Router` etc.) that also has this annotation has an `IdempotentReceiverInterceptor` applied to the associated `MessageHandler.handleMessage(org.springframework.messaging.Message<?>)` method.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/InboundChannelAdapter.html[@InboundChannelAdapter]:: Indicates that a method is capable of producing a `Message` payload.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/IntegrationComponentScan.html[@IntegrationComponentScan]:: Configures component scanning directives for use with `Configuration` classes.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/MessageEndpoint.html[@MessageEndpoint]:: Stereotype annotation indicating that a class is capable of serving as a Message endpoint.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/MessagingGateway.html[@MessagingGateway]:: Provides an Integration Messaging Gateway Proxy (<gateway/>) as an abstraction over the messaging API.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Payloads.html[@Payloads]:: Marks a method parameter as being a list of message payloads, for POJO handlers that deal with lists of messages.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Poller.html[@Poller]:: Provides the `PollerMetadata` options for the Messaging annotations for polled endpoints.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Publisher.html[@Publisher]:: Indicates that a method (or all public methods if applied at class-level) should publish Messages.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/ReleaseStrategy.html[@ReleaseStrategy]:: Indicates that a method is capable of asserting if a list of messages or payload objects is complete.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Role.html[@Role]:: Assigns endpoints to a role. The assigned endpoints can be started and stopped as a group.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Router.html[@Router]:: Indicates that a method is capable of resolving to a channel or channel name based on a message, message header(s), or both.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/ServiceActivator.html[@ServiceActivator]:: Indicates that a method is capable of handling a message or message payload.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Splitter.html[@Splitter]:: Indicates that a method is capable of splitting a single message or message payload to produce multiple messages or payloads.
http://docs.spring.io/spring-integration/api/org/springframework/integration/annotation/Transformer.html[@Transformer]:: Indicates that a method is capable of transforming a message, message header, or message payload.
http://docs.spring.io/spring-integration/api/org/springframework/integration/config/IntegrationConverter.html[@IntegrationConverter]:: Registers `Converter`, `GenericConverter` or `ConverterFactory` beans for the `integrationConversionService`.
https://docs.spring.io/spring-integration/api/org/springframework/integration/jmx/config/EnableIntegrationMBeanExport.html[@EnableIntegrationMBeanExport]:: Enables default exporting for Spring Integration components in an existing application and all @ManagedResource annotated beans.
https://docs.spring.io/spring/docs/4.3.9.RELEASE/javadoc-api/org/springframework/context/annotation/EnableMBeanExport.html[@EnableMBeanExport]:: Enables default exporting of all standard MBeans from the Spring context and all @ManagedResource annotated beans.
http://docs.spring.io/spring-integration/api/org/springframework/integration/support/management/IntegrationManagedResource.html[@IntegrationManagedResource]:: Clone of ManagedResource limiting beans thus annotated so that they will only be exported by the IntegrationMBeanExporter and prevented from being exported by other MBeanExporters (if present).
https://docs.spring.io/spring-integration/api/org/springframework/integration/http/config/EnableIntegrationGraphController.html[@EnableIntegrationGraphController]:: Enables the `IntegrationGraphController` if DispatcherServlet is present in the classpath.


=== Cloud

Spring Cloud includes the following annotations:

{JB: Start here: http://cloud.spring.io/spring-cloud-static/spring-cloud.html}

[horizontal]
https://github.com/spring-cloud/spring-cloud-commons/blob/master/spring-cloud-context/src/main/java/org/springframework/cloud/context/scope/refresh/RefreshScope.java[@RefreshScope]:: Lets beans be refreshed dynamically at runtime.
https://github.com/spring-cloud/spring-cloud-commons/blob/master/spring-cloud-commons/src/main/java/org/springframework/cloud/client/discovery/EnableDiscoveryClient.java[@EnableDiscoveryClient]:: looks for implementations of the `DiscoveryClient` interface via `META-INF/spring.factories`.
http://cloud.spring.io/spring-cloud-static/spring-cloud.html#_embedding_the_config_server[@EnableConfigServer]:: Embeds the Spring Cloud Config Server in another Spring application.
http://cloud.spring.io/spring-cloud-static/spring-cloud.html#_service_discovery_eureka_clients[@EnableEurekaServer]:: Enables the Netflix Eureka Service Discovery client.
https://github.com/spring-cloud/spring-cloud-commons/blob/master/spring-cloud-commons/src/main/java/org/springframework/cloud/client/circuitbreaker/EnableCircuitBreaker.java[@EnableCircuitBreaker]:: Enables a circuit breaker implementation for an application.
http://projects.spring.io/spring-cloud/spring-cloud.html#_circuit_breaker_hystrix_clients[@EnableHystrix]:: Enables the Hystrix circuit breaker. Must go on an application class (such as a class marked with @SpringBootApplication).
http://cloud.spring.io/spring-cloud-static/spring-cloud.html#_circuit_breaker_hystrix_clients[@HystrixCommand]:: Indicates that a bean should be wrapped in a proxy that is connected to the Hystrix circuit breaker.
http://cloud.spring.io/spring-cloud-static/spring-cloud.html#_circuit_breaker_hystrix_clients[@HystrixProperty]:: Sets a property for the @HystrixCommand annotation. See the https://github.com/Netflix/Hystrix/wiki/Configuration[@Hystrix wiki].
http://cloud.spring.io/spring-cloud-static/spring-cloud.html#_circuit_breaker_hystrix_dashboard[@EnableHystrixDashboard]:: Enables the Hystrix dashboard. Must go on a Spring Boot main class.
http://cloud.spring.io/spring-cloud-static/spring-cloud.html#_turbine[@EnableTurbine]:: Enables the Turbine application for a Spring application. Must go on a Spring Boot main class.
http://cloud.spring.io/spring-cloud-static/spring-cloud.html#_turbine_stream[@EnableTurbineStream]:: Enables the Turbine Stream application for a Spring application. Must go on a Spring Boot main class.
https://github.com/spring-cloud/spring-cloud-netflix/blob/master/spring-cloud-netflix-core/src/main/java/org/springframework/cloud/netflix/feign/FeignClient.java[@FeignClient]:: Declares that a REST client should be created for the specified interface.
https://github.com/spring-cloud/spring-cloud-netflix/blob/master/spring-cloud-netflix-core/src/main/java/org/springframework/cloud/netflix/feign/EnableFeignClients.java[@EnableFeignCLients]:: Scans for interfaces that declare they are feign clients. Must go on the application class.
https://github.com/spring-cloud/spring-cloud-netflix/blob/master/spring-cloud-netflix-core/src/main/java/org/springframework/cloud/netflix/ribbon/RibbonClient.java[@RibbonClient]:: Declares a ribbon client. Must go on an @Configuration class.
https://github.com/spring-cloud/spring-cloud-netflix/blob/master/spring-cloud-netflix-core/src/main/java/org/springframework/cloud/netflix/ribbon/RibbonClients.java[@RibbonClients]:: Convenience annotation that combines multiple `@RibbonClient` annotations on a single class (including in Java 7).
https://github.com/spring-cloud/spring-cloud-netflix/blob/master/spring-cloud-netflix-core/src/main/java/org/springframework/cloud/netflix/zuul/EnableZuulProxy.java[@EnableZuulProxy]:: Sets up a Zuul server endpoint and installs some reverse proxy filters in it, so it can forward requests to backend servers. The backends can be registered manually through configuration or via a  `DiscoveryClient`.
https://github.com/spring-cloud/spring-cloud-netflix/blob/master/spring-cloud-netflix-core/src/main/java/org/springframework/cloud/netflix/metrics/atlas/EnableAtlas.java[@EnableAtlas]:: Enables Atlas metrics publishing.
https://github.com/spring-cloud/spring-cloud-stream/blob/master/spring-cloud-stream/src/main/java/org/springframework/cloud/stream/annotation/EnableBinding.java[@EnableBinding]:: Enables the binding of targets annotated with `Input` and `Output` to a broker, according to the list of interfaces passed as value to the annotation.
http://docs.spring.io/spring-cloud-stream/docs/Brooklyn.M1/api/org/springframework/cloud/stream/annotation/StreamListener.html[@StreamListener]:: Indicates a method that is a listener to the inputs declared through `@EnableBinding`.
http://docs.spring.io/spring-cloud-stream/docs/Chelsea.SR2/api/org/springframework/cloud/stream/annotation/Input.html[@Input]:: Indicates that an input binding target will be created by the framework.
http://docs.spring.io/spring-cloud-stream/docs/Chelsea.SR2/api/org/springframework/cloud/stream/annotation/Output.html[@Output]:: Indicates that an output binding target will be created by the framework.
http://docs.spring.io/spring-cloud-stream/docs/Brooklyn.M1/api/org/springframework/cloud/stream/annotation/rxjava/EnableRxJavaProcessor.html[@EnableRxJavaProcessor]:: Class annotation that identifies the class as an RxJava processor module.
https://github.com/spring-cloud/spring-cloud-sleuth/blob/master/spring-cloud-sleuth-zipkin-stream/src/main/java/org/springframework/cloud/sleuth/zipkin/stream/EnableZipkinStreamServer.java[@EnableZipkinStreamServer]:: Enables transporting of spans over a Spring Cloud Stream (such as RabbitMQ).
https://github.com/spring-cloud/spring-cloud-sleuth/blob/master/spring-cloud-sleuth-core/src/main/java/org/springframework/cloud/sleuth/SpanName.java[@SpanName]:: Names a span for use with a stream.
https://github.com/spring-cloud/spring-cloud-commons/blob/master/spring-cloud-commons/src/main/java/org/springframework/cloud/client/loadbalancer/LoadBalanced.java[@LoadBalanced]:: Indicates that a `RestTemplate` bean should be configured to use a `LoadBalancerClient`.

=== Data

Spring includes the following annotations:

[horizontal]
http://docs.spring.io/spring-data/jpa/docs/current/api/org/springframework/data/jpa/repository/config/EnableJpaRepositories.html[@EnableJpaRepositories]:: Class-level annotation that enables JPA repositories. By default, scans the package of the annotated `@Configuration` class for Spring Data repositories.
http://docs.spring.io/spring-data/jpa/docs/current/api/org/springframework/data/jpa/repository/config/EnableJpaAuditing.html[@EnableJpaAuditing]:: Class-level annotation that enables auditing in JPA. Must be on an `@Configuration` class.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/repository/RepositoryDefinition.html[@RepositoryDefinition]:: Indicates the interfaces for which a repository proxy is to be created. Annotating an interface with `@RepositoryDefinition` will cause the same behavior as extending `Repository`.
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/repository/NoRepositoryBean.html[@NoRepositoryBean]:: Indicates an interface for which Spring should not create an instance at runtime.
http://docs.spring.io/spring-data/data-mongo/docs/1.10.4.RELEASE/api/http://docs.spring.io/spring-data/data-mongo/docs/1.10.4.RELEASE/api/org/springframework/data/mongodb/core/mapping/Document.html[@Document]:: Identifies a domain object to be persisted to MongoDB.
http://docs.spring.io/spring-data/data-mongo/docs/1.10.4.RELEASE/api/org/springframework/data/mongodb/core/mapping/DBRef.html[@DBRef]:: Indicates that the annotated field is to be stored using a DBRef.
http://docs.spring.io/spring-data/data-mongo/docs/1.10.4.RELEASE/api/org/springframework/data/mongodb/core/mapping/Field.html[@Field]:: Defines custom metadata for a document field.
http://docs.spring.io/spring-data/data-mongo/docs/1.10.4.RELEASE/api/org/springframework/data/mongodb/core/mapping/Language.html[@Language]:: Marks a property as being a language field.
http://docs.spring.io/spring-data/data-mongo/docs/1.10.4.RELEASE/api/org/springframework/data/mongodb/core/mapping/TextScore.html[@TextScore]:: Marks a property to be considered when doing a full-text search. Important: The property will not be saved when the entity is saved.
http://docs.spring.io/spring-data/mongodb/docs/current/api/org/springframework/data/mongodb/repository/config/EnableMongoRepositories.html[@EnableMongoRepositories]:: Activates MongoDB repositories. If no base package is configured through `value()`, `basePackages()`, or `basePackageClasses()`, it will trigger scanning of the package of annotated class.
http://docs.spring.io/spring-data/jpa/docs/1.11.4.RELEASE/api/org/springframework/data/jpa/repository/Query.html[@Query]:: Declares a finder query on a repository method.
http://docs.spring.io/spring-data/jpa/docs/1.11.4.RELEASE/api/org/springframework/data/jpa/repository/EntityGraph.html[@EntityGraph]:: Configures the JPA 2.1 EntityGraphs that should be used on repository methods.
http://docs.spring.io/spring-data/jpa/docs/1.11.4.RELEASE/api/org/springframework/data/jpa/repository/Lock.html[@Lock]:: Specifies the `LockModeType` to be used when executing a query.
http://docs.spring.io/spring-data/jpa/docs/1.11.4.RELEASE/api/org/springframework/data/jpa/repository/Modifying.html[@Modifying]:: Indicates a method should be regarded as a modifying query.
http://docs.spring.io/spring-data/jpa/docs/1.11.4.RELEASE/api/org/springframework/data/jpa/repository/QueryHints.html[@QueryHints]:: Applies JPA query hints to a query declared in a repository interface.
http://docs.spring.io/spring-data/jpa/docs/1.11.4.RELEASE/api/org/springframework/data/jpa/repository/Temporal.html[@Temporal]:: Declares an appropriate `TemporalType` on query method parameters. Can only be used on parameters of type `Date`.
http://docs.spring.io/spring-data/data-commons/docs/1.13.4.RELEASE/api/org/springframework/data/domain/DomainEvents.html[@DomainEvents]:: Indicates a method that publishes domain events. A method marked with `@AfterDomainEventsPublication` can then be used to manipulated the published events.
http://docs.spring.io/spring-data/data-commons/docs/1.13.4.RELEASE/api/org/springframework/data/domain/AfterDomainEventPublication.html[@AfterDomainEventPublication]:: Indicates a method that manipulates published domain events (often for selecting only events that meet some particular criterion).
http://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/web/config/EnableSpringDataWebSupport.html[@EnableSpringDataWebSupport]:: Automatically register the following beans for usage with Spring MVC: `DomainClassConverter`, `PageableHandlerMethodArgumentResolver`, and `SortHandlerMethodArgumentResolver`. If Spring HATEOAS is on the classpath, it also registers `HateoasPageableHandlerMethodArgumentResolver`, `HateoasSortHandlerMethodArgumentResolver`, `PagedResourcesAssembler`, and `SortHandlerMethodArgumentResolver`.
http://docs.spring.io/spring-data/data-commons/docs/1.13.4.RELEASE/api/org/springframework/data/web/PageableDefault.html[@PageableDefault]:: Set defaults when injecting a `Pageable` into a controller method.
http://docs.spring.io/spring-data/data-commons/docs/1.13.4.RELEASE/api/org/springframework/data/web/SortDefault.html[@SortDefault]:: Defines the default Sort options to be used when injecting a Sort instance into a controller handler method.
http://docs.spring.io/spring-data/data-commons/docs/1.13.4.RELEASE/api/org/springframework/data/web/SortDefault.SortDefaults.html[@SortDefaults]:: Wrapper annotation to allow declaring multiple SortDefault annotations on a method parameter.
http://docs.spring.io/spring-data/data-commons/docs/1.13.4.RELEASE/api/org/springframework/data/web/JsonPath.html[@JsonPath]:: Declares a JSON Path expression on a projection interface.
http://docs.spring.io/spring-data/data-commons/docs/1.13.4.RELEASE/api/org/springframework/data/web/ProjectedPayload.html[@ProjectedPayload]:: Enables projection and projection method annotations that contain JSON or XPath expressions.
http://docs.spring.io/spring-data/data-commons/docs/1.13.4.RELEASE/api/org/springframework/data/querydsl/binding/QuerydslPredicate.html[QuerydslPredicate]:: Customizes the binding of HTTP request parameters to a `Querydsl com.mysema.query.types.Predicate` in Spring MVC handler methods.
http://docs.spring.io/spring-data/jpa/docs/current/api/org/springframework/data/jpa/repository/query/Procedure.html[@Procedure]:: Declares a JPA 2.1 stored procedure mapping directly on a repository method.
http://docs.spring.io/spring-framework/docs/3.2.0.M2/api/org/springframework/transaction/annotation/EnableTransactionManagement.html[@EnableTransactionManagement]:: Enables Spring's annotation-driven transaction management capability.

=== Batch

Spring Batch includes the following annotations:

http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/AfterChunk.html[@AfterChunk]:: Marks a method to be called after a chunk is executed.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/AfterChunkError.html[@AfterChunkError]:: Marks a method to be called after a has failed and been marked for rollback.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/AfterJob.html[@AfterJob]:: Marks a method to be called after a Job has completed.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/AfterProcess.html[@AfterProcess]:: Marks a method to be called after an item is passed to an `ItemProcessor`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/AfterRead.html[@AfterRead]:: Marks a method to be called after an item is read from an `ItemReader`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/AfterStep.html[@AfterStep]:: Marks a method to be called after a `Step` has completed.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/AfterWrite.html[@AfterWrite]:: Marks a method to be called after an item is passed to an `ItemWriter`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/BeforeChunk.html[@BeforeChunk]:: Marks a method to be called before a chunk is executed.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/BeforeJob.html[@BeforeJob]:: Marks a method to be called before a `Job` is executed, which comes after a `JobExecution` is created and persisted, but before the first `Step` is executed.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/BeforeProcess.html[@BeforeProcess]:: Marks a method to be called before an item is passed to an `ItemProcessor`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/BeforeRead.html[@BeforeRead]:: Marks a method to be called before an item is read from an `ItemReader`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/BeforeStep.html[@BeforeStep]:: Marks a method to be called before a `Step` is executed, which comes after a `StepExecution` is created and persisted, but before the first item is read.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/BeforeWrite.html[@BeforeWrite]:: Marks a method to be called before an item is passed to an `ItemWriter`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/OnProcessError.html[@OnProcessError]:: Marks a method to be called if an exception is thrown by an `ItemProcessor`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/OnReadError.html[@OnReadError]:: Marks a method to be called if an exception is thrown by an `ItemReader`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/OnSkipInProcess.html[@OnSkipInProcess]:: Marks a method to be called when an item is skipped due to an exception thrown in the `ItemProcessor`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/OnSkipInRead.html[@OnSkipInRead]:: Marks a method to be called when an item is skipped due to an exception thrown in the `ItemReader`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/OnSkipInWrite.html[@OnSkipInWrite]:: Marks a method to be called when an item is skipped due to an exception thrown in the `ItemWriter`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/annotation/OnWriteError.html[@OnWriteError]:: Marks a method to be called if an exception is thrown by an `ItemWriter`.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/configuration/annotation/EnableBatchProcessing.html[@EnableBatchProcessing]:: Enable Spring Batch features and provide a base configuration for setting up batch jobs in an `@Configuration` class, roughly equivalent to using the `<batch:*>` XML namespace.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/configuration/annotation/JobScope.html[@JobScope]:: Convenience annotation for job-scoped beans that defaults the proxy mode, so that it doesn't have to be specified explicitly on every bean definition.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/core/configuration/annotation/StepScope.html[@StepScope]:: Convenience annotation for step-scoped beans that defaults the proxy mode, so that it doesn't have to be specified explicitly on every bean definition.
http://docs.spring.io/spring-batch/trunk/apidocs/org/springframework/batch/support/annotation/Classifier.html[@Classifier]:: Mark a method as capable of classifying its input to an instance of its output.

=== Aspect-oriented Programming

Spring includes a set of annotations for working with Aspect-oriented Programming (AOP):

[horizontal]
https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/context/annotation/EnableAspectJAutoProxy.html[@EnableAspectJAutoProxy]:: Enables support for handling components marked with AspectJ's @Aspect annotation. Must be used on a class that is also marked with the @Configuration annotation (or another annotation that includes the @Configuration annotation).
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-at-aspectj[@Aspect]:: Indicates that a class is an aspect.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-pointcuts[@Pointcut]:: Defines a join point.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-pointcuts-designators[@target]:: Limits matching to join points. (Not to be confused with @Target for @Configuration classes.)
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-pointcuts-designators[@args]:: Limits matching to join points
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-pointcuts-designators[@within]:: Limits matching to join points within types that have the given annotation.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-pointcuts-designators[@annotation]:: limits matching to join points where the subject of the join point has the given annotation
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-ajlib-other[@Transactional]:: Class annotation that specifies the default transaction semantics for the execution of any public operation in the class.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-advice-before[@Before]:: Declares pointcut advice that should run before methods matched by the pointcut.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-advice-after-returning[@AfterReturning]:: Declares pointcut advice that should run after the methods matched by the pointcut. The methods must return normally. See @AfterThrowing and @After.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-schema-advice-after-throwing[@AfterThrowing]:: Declares pointcut advice that should run after the methods matched by the pointcut have thrown an exception.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-schema-advice-after-finally[@After]:: Declares pointcut advice to run after the methods matched by the pointcut have run, whether they returned normally or threw an exception. Parallel to `finally` in a try-catch-finally block.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-ataspectj-around-advice[@Around]:: Declares advice that runs around (potentially both before and after) the methods matched by the pointcut. Can also determine if pointcut methods run. Do not use if @Before or @After suffice.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-introductions[@DeclareParents]:: Declares that matching types have a new parent.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/aop.html#aop-atconfigurable[@Configurable]:: Marks a class as eligible for Spring-driven configuration.
http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/context/annotation/aspectj/EnableSpringConfigured.html[@EnableSpringConfigured]:: Tells the current application context to apply dependency injection to non-managed classes that are instantiated outside of the Spring bean factory.

=== Integration Testing

Spring includes a set of annotations for working with integration testing:

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__bootstrapwith[@BootstrapWith]:: Specifies a custom `TestContextBootstrapper` class.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__contextconfiguration[@ContextConfiguration]:: Defines class-level metadata that determines how to load and configure an `ApplicationContext` for integration tests.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__webappconfiguration[@WebAppConfiguration]:: Class-level annotation that is used to declare that the `ApplicationContext` loaded for an integration test should be a `WebApplicationContext`.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__contexthierarchy[@ContextHierarchy]:: Class-level annotation that defines a hierarchy of ApplicationContexts for integration tests.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__activeprofiles[@ActiveProfiles]:: Class-level annotation that indicates which bean definition profiles should be active.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__testpropertysource[@TestPropertySource]:: Class-level annotation that configures the locations of properties files and inlined properties to be added to the set of PropertySources in the Environment for an ApplicationContext loaded for an integration test.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__dirtiescontext[@DirtiesContext]:: Indicates that the underlying Spring ApplicationContext has been modified or corrupted in some manner during the execution of a test and should be closed. When an application context is marked as dirty, it is removed from the testing framework’s cache and closed.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__testexecutionlisteners[@TestExecutionListeners]:: Defines class-level metadata for configuring the TestExecutionListener implementations that should be registered with the TestContextManager.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__commit[@Commit]:: Causes a transaction to commit rather than rollback during testing. Use only when you want a test to modify a database. See @Rollback.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__rollback[@Rollback]:: indicates whether the transaction for a transactional test method should be rolled back after the test method has completed. See @Commit.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__beforetransaction[@BeforeTransaction]:: Indicates that the annotated void method should be executed before a transaction is started for test methods configured to run within a transaction via Spring’s `@Transactional` annotation.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__aftertransaction[@AfterTransaction]:: Indicates that the annotated void method should be executed after a transaction is ended for test methods configured to run within a transaction via Spring’s `@Transactional` annotation.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__sql[@Sql]:: Annotates a test class or test method to configure SQL scripts to be executed against a given database during integration tests.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__sqlconfig[@SqlConfig]:: Defines metadata that is used to determine how to parse and execute SQL scripts configured via the `@Sql` annotation.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__sqlgroup[@SqlGroup]:: Container annotation that aggregates several `@Sql` annotations.

=== Unit Testing

Spring includes a set of annotations for unit testing:

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__ifprofilevalue[@IfProfileValue]:: Indicates that, if the value returned by the `name` argument matches the value of the `value` argument, the annotated test is enabled for a specific testing environment.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__profilevaluesourceconfiguration[@ProfileValueSourceConfiguration]:: Class-level annotation that specifies what type of ProfileValueSource to use when retrieving profile values configured through the `@IfProfileValue` annotation.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__timed[@Timed]:: Indicates that the annotated test method must finish execution in a specified time period (in milliseconds).
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/integration-testing.html#__repeat[@Repeat]:: Indicates that the annotated test method must be executed a number of times.

=== JMX

Spring includes a set of annotations for working with Java Managed Extensions (JMX):

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/jmx.html#jmx-interface-metadata-types[@ManagedResource]:: Marks all instances of a Class as JMX managed resources.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/jmx.html#jmx-interface-metadata-types[@ManagedAttribute]:: Mark a getter or setter as one half of a JMX attribute.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/jmx.html#jmx-interface-metadata-types[@ManagedOperation]:: Mark a method as a JMX operation.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/jmx.html#jmx-interface-metadata-types[@ManagedOperationParameters]:: Define descriptions for operation parameters.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/jmx.html#jmx-interface-metadata-types[@ManagedOperationParameter]:: Define the descriptions for an operation parameter.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/jmx.html#jmx-context-mbeanexport[@EnableMBeanExport]:: Class-level application that indicates whether an application is an exporter of managed beans.

=== Task Execution and Scheduling

Spring includes a set of annotations to support task execution and scheduling:

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/scheduling.html#scheduling-annotation-support-scheduled[@Scheduled]:: Indicates that a method should be called on a scheduled basis.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/scheduling.html#scheduling-annotation-support-async[@Async]:: Indicates that a method may be called asynchronously.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/scheduling.html#scheduling-enable-annotation-support[@EnableScheduling]:: Enables support for the `@Schedule` annotation.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/scheduling.html#scheduling-enable-annotation-support[@EnableAsync]:: Enables support for the `@Async` annotation.

=== Cache Abstraction

Spring includes a set of annotations for working with caching:

[horizontal]
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-annotations-cacheable[@Cacheable]:: Indicates a method whose result is cacheable.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-annotations-evict[@CacheEvict]:: Indicates that a method performs cache eviction (removes items from a cache).
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-annotations-put[@CachePut]:: Indicates a method whose result will always be put in a cache.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-annotations-caching[@Caching]:: Allows multiple nested `@Cacheable`, `@CachePut` and `@CacheEvict` to be used on the same method
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-annotations-config[@CacheConfig]:: Class-level annotation that allows sharing of the cache names, the custom KeyGenerator, the custom CacheManager, and the custom CacheResolver. Placing this annotation on the class does not turn on any caching operation. See @EnableCaching.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-annotation-enable[@EnableCaching]:: Turns on caching in an application. Must go on an `@Configuration` class.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-jsr-107-summary[@CacheResult]:: Similar to `@Cacheable` but can cache specific exceptions and force the execution of the method regardless of the content of the cache.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-jsr-107-summary[@CacheRemove]:: Similar to `@CacheEvict` but can support conditional removal if the method throws an exception.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-jsr-107-summary[@CacheRemoveAll]:: Similar to `@CacheEvict(allEntries=true)` but can support conditional removal if the method throws an exception.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-jsr-107-summary[@CacheDefaults]:: Similar to `@CacheConfig`.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-jsr-107-summary[@CacheValue]:: Usable with @CachePut to update the cache before or after method invocation.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html#cache-jsr-107-summary[@CacheKey]:: Optional method parameter annotation to indicate which argument(s) should be the key. (The default is to construct the key from all the parameters, unless one or more parameters are marked with `@CacheKey`.)

=== Other

Spring includes a few other annotations that don't fit into the preceding categories:

[horizontal]
https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/bind/annotation/ExceptionHandler.html[@ExceptionHandler]:: Annotation for handling exceptions in specific handler classes and/or handler methods.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/validation.html#format[@NumberFormat]:: Declares that a field or method parameter should be formatted as a number.
https://docs.spring.io/spring/docs/current/spring-framework-reference/html/validation.html#format[@DateTimeFormat]:: Declares that a field or method parameter should be formatted as a date or time.
