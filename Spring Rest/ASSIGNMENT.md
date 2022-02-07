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

**3**
.CRATE A RESTFULWEB SERVICES THAT RETURNS STATE,CITY AND COUNTRY INFORMATION WHEN USER PASES ZIPCODE .STATE CITY COUNTRY IN JSON FORMAT

**5**
.Develop RESTful web services for “Employee Management System” that manages the information about employees.

- 1.Add a new employee
- 2.Searching for specific employee
-3.Deleting an existing employee
- 4.Finding all employees
  -5.Editing/Updating employee information.
Create a Employee domain model class having following properties: employeeId, employeeName, employeeDepartment, employeeDesignation, employeeSalary . Employee Id should be generated automatically at database level. Develop controller, service and repository layers classes. Use CrudRepository from Spring Data.

```JAVA
//EMPLOYEE.JAVA
package com.example.assign5.emp;

import javax.persistence.Entity;
import javax.persistence.Id;

@Entity
public class Employee {
	
	@Id
	int employeeId;
	String employeeName;
	String employeeDepartment;
	String employeeDesignation;
	int employeeSalary;
	
	public Employee() {
		
	}
	public Employee(int employeeId, String employeeName, String employeeDepartment, String employeeDesignation,
			int employeeSalary) {
		super();
		this.employeeId = employeeId;
		this.employeeName = employeeName;
		this.employeeDepartment = employeeDepartment;
		this.employeeDesignation = employeeDesignation;
		this.employeeSalary = employeeSalary;
	}
	public int getEmployeeId() {
		return employeeId;
	}
	public void setEmployeeId(int employeeId) {
		this.employeeId = employeeId;
	}
	public String getEmployeeName() {
		return employeeName;
	}
	public void setEmployeeName(String employeeName) {
		this.employeeName = employeeName;
	}
	public String getEmployeeDepartment() {
		return employeeDepartment;
	}
	public void setEmployeeDepartment(String employeeDepartment) {
		this.employeeDepartment = employeeDepartment;
	}
	public String getEmployeeDesignation() {
		return employeeDesignation;
	}
	public void setEmployeeDesignation(String employeeDesignation) {
		this.employeeDesignation = employeeDesignation;
	}
	public int getEmployeeSalary() {
		return employeeSalary;
	}
	public void setEmployeeSalary(int employeeSalary) {
		this.employeeSalary = employeeSalary;
	}
	
}
```
//EMPLOYEECONTROLLER.JAVA
package com.example.assign5.emp;
	
import java.util.Arrays;
import java.util.List;
import java.util.Optional;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

//import com.example.assign5.emp.*;

@RestController
public class EmployeeController {
	
	@Autowired
	private EmployeeService employeeService;
	
	@RequestMapping("/emp")
	public List<Employee> getAllEmp(){
		return employeeService.getAllEmp();
	}
	@RequestMapping("/emp/{employeeId}")
	public Optional<Employee> getEmp(@PathVariable int employeeId) {
		return employeeService.getEmp(employeeId);
	}
	
	@RequestMapping(method = RequestMethod.POST, value="/emp")
	public void addEmp(@RequestBody Employee emp) {
		employeeService.addEmp(emp);
	}
	
	@RequestMapping(method = RequestMethod.PUT, value="/emp/{employeeId}")
	public void updateEmp(@RequestBody Employee emp, @PathVariable int employeeId) {
		employeeService.updateEmp(employeeId,emp);
	}
	
	@RequestMapping(method = RequestMethod.DELETE, value="/emp/{employeeId}")
	public void deleteEmp(@PathVariable int employeeId) {
		employeeService.deleteEmp(employeeId);
	}
	
	}
```
```
//EMPLOEEREPOSITORY.JAVA
package com.example.assign5.emp;
	
import org.springframework.data.repository.CrudRepository;

public interface EmployeeRepository extends CrudRepository<Employee, Integer>{
	
	
}
```
```
EmployeeService.java
package com.example.assign5.emp;
	
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.Optional;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;


@Service
public class EmployeeService {
	
	@Autowired
	private EmployeeRepository employeeRepository;
	
	/*private List<Employee> emps = new ArrayList<>(Arrays.asList(
			new Employee(15,"Manu","HR","Manager",20000),
			new Employee(12,"Sam","Training","Trainee",15000),
			new Employee(14,"Anu","IT","Developer",30000)
			));*/
	
	// 4. finding all employees
	public List<Employee> getAllEmp(){
		//return emps;
		List<Employee> emps = new ArrayList<>();
		employeeRepository.findAll()
		.forEach(emps::add);
		return emps;
		
		}
	
	//2. Searching for specific employee	
 public Optional<Employee> getEmp(int employeeId) {
	//return emps.stream().filter(e -> e.getEmployeeId() == (employeeId)).findFirst().get();
	 return employeeRepository.findById(employeeId);
 }
 
 //1. adding new employee
 public void addEmp(Employee emp) {
	 //emps.add(emp);
	 employeeRepository.save(emp);
 }
 
 //5. update the employee information 
 public void updateEmp(int employeeId, Employee emp) {
	/*	for(int i = 0; i < emps.size();i++) {
			Employee e = emps.get(i);
			if(e.getEmployeeId()==(employeeId)) {
				emps.set(i, emp);
				return;
			}
		}*/
	 employeeRepository.save(emp);
 }
 
 // 3. delete the employee
 public void deleteEmp(int employeeId) {
	// emps.removeIf(e -> e.getEmployeeId() == (employeeId));
	 employeeRepository.deleteById(employeeId);;
 }
 
}
```
**Q7**
Design and develop RESTful webservice as follows.

A user can place an order
A user can update an order.
A user can view specific order.
A user can view all the orders.
A user can delete a specific order.
	
```	
//User.java
package com.example.assign7.us;
	
import org.springframework.data.annotation.Id;
import org.springframework.data.mongodb.core.mapping.Document;
import org.springframework.data.mongodb.core.mapping.Field;

@Document
public class User {
		@Id
	    private String orderid;
	    @Field
	    private String orderaddress;
	    @Field
	    private String ordercost;
	    public User(){} 
	    
	    public User(String orderaddress, String ordercost) {
	        super();
	        this.orderaddress = orderaddress;
	        this.ordercost = ordercost;
	    }

	 

	    @Override
	    public String toString() {
	        return String.format("User[orderid='%s',orderaddress='%s',usercost='%s']",orderid,orderaddress,ordercost);
	    }
	    public String getOrderid() {
	        return orderid;
	    }
	    public void setOrderid(String orderid) {
	        this.orderid = orderid;
	    }
	    public String getOrderaddress() {
	        return orderaddress;
	    }
	    public void setOrderaddress(String orderaddress) {
	        this.orderaddress = orderaddress;
	    }
	    public String getOrdercost() {
	        return ordercost;
	    }
	    public void setOrdercost(String ordercost) {
	        this.ordercost = ordercost;
	    }

}
```
//USERREPOSITORY.JAVA
package com.example.assign7.us;

import org.springframework.data.mongodb.repository.MongoRepository;

public interface UserRepository extends MongoRepository<User,String>{

}

```
```
APPLICATIONPROPETIES
spring.data.mongodb.uri=mongodb+srv://Manisha:Manu#1999@cluster0.d6fbp.mongodb.net/datab01?retryWrites=true&w=majority
```

**Q9**
Design and develop RESTful web service as follows: 1. Add a new customer information. 2. Update customer information. 3. Delete existing customer information 4. Fetch information of specific customer. 5. Fetch information of all customers. Note: Use CrudRepository of Spring Data to store customer details.
```JAVA
Customer.java
package com.example.assign9.cust;
import javax.persistence.Entity;
import org.springframework.data.annotation.Id;
@Entity
public class Customer {
	
	@Id
	private String cust_id;
	private String cust_name;
	private String cust_phone;
	
	public Customer()
	{
		
	}
	
	public Customer(String cust_id, String cust_name, String cust_phone)
	{
		this.setCust_id(cust_id);
		this.setCust_name(cust_name);
		this.setCust_phone(cust_phone);
	}

	public String getCust_id() {
		return cust_id;
	}

	public void setCust_id(String cust_id) {
		this.cust_id = cust_id;
	}

	public String getCust_name() {
		return cust_name;
	}

	public void setCust_name(String cust_name) {
		this.cust_name = cust_name;
	}

	public String getCust_phone() {
		return cust_phone;
	}

	public void setCust_phone(String cust_phone) {
		this.cust_phone = cust_phone;
	}

}
```
```
//CUSTOMER.JAVA
package com.example.assign9.cust;

import java.util.List;
import java.util.Optional;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;


@RestController
public class CustomerController {

@Autowired
private CustomerService customerService;

@RequestMapping("/cus")
public List<Customer> getAllCus(){
	return customerService.getAllCus();
}
@RequestMapping("/cus/{cust_id}")
public Optional<Customer> getCus(@PathVariable String cust_id) {
	return customerService.getCus(cust_id);
}

@RequestMapping(method = RequestMethod.POST, value="/cus")
public void addCus(@RequestBody Customer cust) {
	customerService.addCus(cust);
}

@RequestMapping(method = RequestMethod.PUT, value="/cus/{cust_id}")
public void updateCus(@RequestBody Customer cust, @PathVariable String cust_id) {
	customerService.updateCus(cust_id,cust);
}

@RequestMapping(method = RequestMethod.DELETE, value="/cus/{cust_id}")
public void deleteCus(@PathVariable String cust_id) {
	customerService.deleteCus(cust_id);
}
}
```
```
//CUSTOMERREPOSITORY.JAVA
package com.example.assign9.cust;
import org.springframework.data.repository.CrudRepository;
public interface CustomerRepository extends CrudRepository<Customer, String>{

}
```
```
//CUSTOMERSERVICE.JAVA
	package com.example.assign9.cust;
	
import java.util.ArrayList;
import java.util.List;
import java.util.Optional;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;


@Service
public class CustomerService {

	@Autowired
	private CustomerRepository customerRepository;
	
	
	
	// 4. fetch information all customers
	public List<Customer> getAllCus(){
		
		List<Customer> custo = new ArrayList<>();
		customerRepository.findAll()
		.forEach(custo::add);
		return custo;
		
		}
	
	//2. fetch information for specific employee	
 public Optional<Customer> getCus(String cust_id) {
	
	 return customerRepository.findById(cust_id);
 }
 
 //1. adding new customer information
 public void addCus(Customer cus) {
	 
	 customerRepository.save(cus);
 }
 
 //5. update the customer information 
 public void updateCus(String cust_id, Customer cus) {
	
	 customerRepository.save(cus);
 }
 
 // 3. delete the customer information
 public void deleteCus(String cust_id) {
	
	 customerRepository.deleteById(cust_id);;
 }
}
```
	
	
