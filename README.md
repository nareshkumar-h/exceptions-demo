#  Exceptions Demo

##### Without Exception
```java
package in.naresh;

public class TestRuntimeException {

	public static void main(String[] args) {

		String ageStr = "14";
		
		int age = Integer.parseInt(ageStr);
		
		System.out.println(age);
		
	}

}
```

#####  Exception 1: RuntimeException Category = >Invalid Input .. Exception will get raised

```java
package in.naresh;

public class TestRuntimeException {

	public static void main(String[] args) {

		String ageStr = "f14";
		
		int age = Integer.parseInt(ageStr);
		
		System.out.println(age);
		
	}

}

```

```java
Exception in thread "main" java.lang.NumberFormatException: For input string: "f14"
	at java.base/java.lang.NumberFormatException.forInputString(NumberFormatException.java:68)
	at java.base/java.lang.Integer.parseInt(Integer.java:652)
	at java.base/java.lang.Integer.parseInt(Integer.java:770)
	at in.naresh.TestRuntimeException.main(TestRuntimeException.java:9)

```

###### Explain NumberFormatException
```
public class NumberFormatException extends IllegalArgumentException { }
public class IllegalArgumentException extends RuntimeException {}
public class RuntimeException extends Exception
```

##### Do we need to add try/catch or not ?
* IF YOU ARE GOING TO GET EXCEPTIONS which extends RuntimeException ( Compiler will not force you to add try/catch or declare exception )


##### Exception 2: Checked Exception
```
package in.naresh;

public class TestException {

	public static void main(String[] args) {
		
		
		//Exceptions which extend Exception class are called checked Exceptions
		//Compiler will force to handle the exception 
		//ClassNotFoundException extends... Exception
		
		try {
			Class.forName("com.postgresql.Driver");
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}

}
```
![Uploading exception.png…]()



