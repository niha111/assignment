# Q1
CREATE A RESTFUL WEB SERVICES THAT RETURNS "HELLO WORLD" MESSAGE.

**HELLO WORLD**
```
--Hellworld.java
package com.javahello;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController

public class Hellworld {

	@RequestMapping("/hello")
	public String redirect() {
		return "helloWorld";
	}
 }
 ```
 **spring-dispatcher-servlet.xml**
```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"  
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns:context="http://www.springframework.org/schema/context"  
    xmlns:mvc="http://www.springframework.org/schema/mvc"  
    xsi:schemaLocation="  
        http://www.springframework.org/schema/beans  
        http://www.springframework.org/schema/beans/spring-beans.xsd  
        http://www.springframework.org/schema/context  
        http://www.springframework.org/schema/context/spring-context.xsd  
        http://www.springframework.org/schema/mvc  
        http://www.springframework.org/schema/mvc/spring-mvc.xsd">  
  
    <!-- Provide support for component scanning -->  
    <context:component-scan base-package="com.javahello" />  
  
    <!--Provide support for conversion, formatting and validation -->  
    <mvc:annotation-driven/>  
<!-- Define Spring MVC view resolver -->  
<bean id="viewResolver" class="org.springframework.web.servlet.view.InternalResourceViewResolver">  
        <property name="prefix" value="/WEB-INF/"></property>  
        <property name="suffix" value=".jsp"></property>          
     </bean>  
</beans>
```
**web.xml**
```
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://xmlns.jcp.org/xml/ns/javaee" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd" id="WebApp_ID" version="4.0">
  <display-name>HellWorld</display-name>
  <servlet>
 	<servlet-name>spring-dispatcher</servlet-name>
 		<servlet-class>
 			org.springframework.web.servlet.DispatcherServlet
 		</servlet-class>
 </servlet>
 
 <servlet-mapping>
 	<servlet-name>spring-dispatcher</servlet-name>
 	<url-pattern>/</url-pattern>
 </servlet-mapping>
 </web-app>
 ```
 
 # Q2
 RESTFUL WEBSERVICES THAT AUTHENTICATE AN USER USER WILL SPECIFY HIS/HER CREDENTIALS WERE CORRECT IT RETURN VALID USER MESSAGE, ELSE INVALID USER
 
 **H2.JAVA**
 ```
 package com.qq;



import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.servlet.ModelAndView;
@RestController
public class H2 {

@RequestMapping(value = "/getjson.html", method = RequestMethod.GET)
public ModelAndView getForm() 
{
ModelAndView model = new ModelAndView("Credentials");
return model;
}
@RequestMapping(value = "/submitjson1.html", method = RequestMethod.POST)
public String acceptForm(@RequestParam("username") String username, @RequestParam("password") String password)
{
String user = "niha";
String pass = "gopalam";
if(username.equals(user) && password.equals(pass))
{
String s = "HI USWER, IKNOW YOU";
return s;
}
else
{
String f = "WHO ARE YOU";
return f;
}
}
}
```
**CREDENTIALS.JSP**
```
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="ISO-8859-1">
<title>Insert title here</title>
</head>
<body>
<form action = "/2Q/submitjson.html" method = "post">

<p> Username : <input type = "text" name = "username"/></p>
<p> Password : <input type = "password" name = "password"/></p>
<input type = "submit" value = "Submit"/>


</body>
</html>
```
**SPRING-DISPATCHER-SERVLET.XML**
```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"  
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns:context="http://www.springframework.org/schema/context"  
    xmlns:mvc="http://www.springframework.org/schema/mvc"  
    xsi:schemaLocation="  
        http://www.springframework.org/schema/beans  
        http://www.springframework.org/schema/beans/spring-beans.xsd  
        http://www.springframework.org/schema/context  
        http://www.springframework.org/schema/context/spring-context.xsd  
        http://www.springframework.org/schema/mvc  
        http://www.springframework.org/schema/mvc/spring-mvc.xsd">  
  
    <!-- Provide support for component scanning -->  
    <context:component-scan base-package="com.qq" />  
  
    <!--Provide support for conversion, formatting and validation -->  
    <mvc:annotation-driven/>  
<!-- Define Spring MVC view resolver -->  
<bean id="viewResolver" class="org.springframework.web.servlet.view.InternalResourceViewResolver">  
        <property name="prefix" value="/WEB-INF/"></property>  
        <property name="suffix" value=".jsp"></property>          
     </bean>  
</beans>
```

**WEB.XML**
```
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://xmlns.jcp.org/xml/ns/javaee" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd" id="WebApp_ID" version="4.0">
  <display-name>2Q</display-name>
 
  <servlet>
 	<servlet-name>spring-dispatcher</servlet-name>
 		<servlet-class>
 			org.springframework.web.servlet.DispatcherServlet
 		</servlet-class>
 </servlet>
 
 <servlet-mapping>
 	<servlet-name>spring-dispatcher</servlet-name>
 	<url-pattern>/</url-pattern>
 </servlet-mapping>
 
 
</web-app>
```

3.CRATE A RESTFULWEB SERVICES THAT RETURNS STATE,CITY AND COUNTRY INFORMATION WHEN USER PASES ZIPCODE .STATE CITY COUNTRY IN JSON FORMAT
 
 
 
 
 
