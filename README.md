# iocproj06-singletonclass-corejava
 
# code
```java
package com.printer.client;

import com.printer.ston.Printer;

public class SingletonDPTest 
{
    public static void main( String[] args )
    {
        // try  to create multiple object by calling static factory methods for mutliple times
    	 Printer printer1=Printer.getInstance();
    	 Printer printer2=Printer.getInstance();
    	 Printer printer3=Printer.getInstance();
    	 System.out.println(printer1.hashCode()+"  "+printer2.hashCode()+"  "+printer3.hashCode());
    	 System.out.println("printer1==printer2?"+(printer1==printer2));
    	 System.out.println("printer2==printer3?"+(printer2==printer3));
    }
}

```

```Java
package com.printer.ston;

public class Printer {
	// private static ref variable to that single obj
	private static Printer INSTANCE;

	private Printer() {
		System.out.println("Printer:: 0-param constructor");
	}

	// public static factory method having singleton logic
	public static Printer getInstance() {
		// singleton logic
		if (INSTANCE == null)
			INSTANCE = new Printer();

		return INSTANCE;
	}

	// b.method
	public void printMessage(String msg) {
		System.out.println(msg);
	}

}
```

# dependencies
```xml
	<dependencies>
		<!-- https://mvnrepository.com/artifact/junit/junit -->
		<dependency>
			<groupId>junit</groupId>
			<artifactId>junit</artifactId>
			<scope>test</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

```

# UML
![UML](/src/main/resources/UML.png)
