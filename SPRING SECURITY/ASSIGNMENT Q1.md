 
# helloworld using default login form
![Screenshot (6)](https://user-images.githubusercontent.com/97155964/152315582-8863dfc7-1553-4200-84a0-288a736e5027.png)
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

**Hello.java
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




