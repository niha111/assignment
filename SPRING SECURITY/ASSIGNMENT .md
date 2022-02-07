# Spring Security Assignment

**Q1**
helloworld using default CREDENTIALS

![Screenshot (8)](https://user-images.githubusercontent.com/97155964/152315921-2888d93c-fd83-4bf3-a8d3-1033180ca096.png)


```xml
POM.XML

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.6.3</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.niha</groupId>
	<artifactId>boot</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>boot</name>
	<description>Hello World</description>
	<properties>
		<java.version>11</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
    <version>2.6.3</version>
</dependency>
		

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
```

**Hello.java **
```
package com.niha.boot;

import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController

	public class Hello {

		@RequestMapping("/hello")
		public String redirect() {
			return "hello world";
		}
		}
```

bootapplication.java
```
package com.niha.boot;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class BootApplication {

	public static void main(String[] args) {
		SpringApplication.run(BootApplication.class, args);
	}

}
```
![Screenshot (9)](https://user-images.githubusercontent.com/97155964/152316393-59719953-1679-4253-98c5-b78efde58c2f.png)
![Screenshot (10)](https://user-images.githubusercontent.com/97155964/152316471-25405cf8-ae8d-4e1d-ac73-3fe2a231c64e.png)
![Screenshot (11)](https://user-images.githubusercontent.com/97155964/152316602-94d5e436-36d0-4d73-83c0-422a5390df02.png)
![Screenshot (12)](https://user-images.githubusercontent.com/97155964/152316684-2266618c-6a1c-4fbe-9f52-4c18c638b963.png)


# 2nd question

**by using custom credentials **

for using custom credentials we need to modify the application.properties


```
application.properties

spring.security.user.name=niharika
spring.security.user.password=gopalm
```

![Screenshot (13)](https://user-images.githubusercontent.com/97155964/152323198-38e5dc5f-fa56-4d63-b9a7-8d3bcec83d7f.png)
![Screenshot (14)](https://user-images.githubusercontent.com/97155964/152323220-ca8ff1e0-f578-4594-a53c-c9f6cf131bc6.png)

**Q3**
Modify the above application and use database authentication using JDBC instead of in memory authentication. User Java Based and annotation based configuration and In-memory authentication. 
```JAVA
//HomeResource.java
package com.example.springsecurityques3;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;
@RestController
public class HomeResource {
	@GetMapping("/page")
	 public String viewLoginPage() {     
	      return "login";
	  }
		
		@GetMapping("/user")
	  public String viewuserLoginPage() {     
	      return "login";
	  }
		
		@GetMapping("/admin")
	  public String viewadminLoginPage() {     
	      return "login";
	  }
}
```
```JAVA
//MYCONFIG.JAVA
package com.example.springsecurityques3;

import org.springframework.context.annotation.Configuration;
import org.springframework.web.servlet.config.annotation.ViewControllerRegistry;
import org.springframework.web.servlet.config.annotation.WebMvcConfigurer;
@Configuration
public class MyConfig implements WebMvcConfigurer{

@Override
public void addViewControllers(ViewControllerRegistry registry) {
registry.addViewController("/login").setViewName("login");
}
public void addViewuser(ViewControllerRegistry registry) {
registry.addViewController("/user").setViewName("login");
}
public void addViewadmin(ViewControllerRegistry registry) {
registry.addViewController("/admin").setViewName("login");
}
}
```
```
//SECURITYCONFIGURATION.JAVA
package com.example.springsecurityques3;
	
import javax.sql.DataSource;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.security.config.annotation.authentication.builders.AuthenticationManagerBuilder;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.EnableWebSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;
import org.springframework.security.crypto.password.NoOpPasswordEncoder;
import org.springframework.security.crypto.password.PasswordEncoder;

@Configuration
@EnableWebSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
	@Autowired
	DataSource datasource;

	@Override
	protected void configure(AuthenticationManagerBuilder auth) throws Exception {
		// TODO Auto-generated method stub
		auth.jdbcAuthentication()
		.dataSource(datasource);
		}

	@Override
	protected void configure(HttpSecurity http) throws Exception {
		// TODO Auto-generated method stub
	http.authorizeRequests().antMatchers("/admin").hasRole("ADMIN")
	.antMatchers("/user").hasAnyRole("ADMIN","USER")
	.antMatchers("/").permitAll()
	.and().formLogin().loginPage("/login")
	.usernameParameter("username").permitAll()
	.and().logout().permitAll();
	}
	
	@Bean
	public PasswordEncoder getPasswordEncoder() {
		return NoOpPasswordEncoder.getInstance();
	}	
}
```
```
//LOGIN.HTML
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0">
    <title>Login </title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
        integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
        crossorigin="anonymous" />
</head>
<body>
<div class="container-fluid text-center" align="center">
    <form th:action="@{/login}" method="post" style="max-width: 300px; margin: 0 auto;">
        
        </div>
        <div class="border border-secondary p-3 rounded">
            <p>
                <input type="username" name="username" class="form-control" placeholder="UserName" required />
            </p>
            <p>
                <input type="password" name="password" class="form-control" placeholder="Password" required />
            </p>
            <p>
                <input type="checkbox" name="remember-me" />&nbsp;Remember Me
            </p>
            <p>
                <input type="submit" value="Login" class="btn btn-primary" />
            </p>
        </div>
       
    </form>      
</div>
</body>
</html>
```
```
//DATA.SQL
INSERT INTO users(username,password,enabled)
values('user','pass',true);
	
INSERT INTO users(username,password,enabled)
values('admin','admin123',true);

INSERT INTO authorities(username,authority)
values('user','ROLE_USER');

INSERT INTO authorities(username,authority)
values('admin','ROLE_ADMIN');
```
```
//SCHEMA.SQL
create table users(
	username varchar_ignorecase(50) not null primary key,
	password varchar_ignorecase(50) not null,
	enabled boolean not null
);	
create table authorities (
	username varchar_ignorecase(50) not null,
	authority varchar_ignorecase(50) not null,
	constraint fk_authorities_users foreign key(username) references users(username));
create unique index ix_auth_username on authorities (username,authority);
```


